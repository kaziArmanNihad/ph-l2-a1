TypeScript এ Access Modifiers (public, private, protected, এবং readonly) এর ব্যবহার

Object Oriented Programming (OOP) এ ডেটা এনক্যাপসুলেশন (Data Encapsulation) একটি অত্যন্ত গুরুত্বপূর্ণ বিষয়। TypeScript এ ডেটার সুরক্ষা নিশ্চিত করতে এবং অ্যাক্সেস নিয়ন্ত্রণ করার জন্য প্রধানত চার ধরনের Access Modifier ব্যবহার করা হয়। এগুলো হলো: public, private, protected এবং readonly।

১. Public (পাবলিক):
এটি TypeScript এর ডিফল্ট মডিফায়ার। কোনো প্রপার্টি বা মেথডের আগে public লেখা থাকলে সেটি ক্লাসের ভেতরে এবং বাইরে যেকোনো জায়গা থেকে অনায়াসে অ্যাক্সেস করা যায়।

২. Private (প্রাইভেট):
private মডিফায়ার যুক্ত প্রপার্টি শুধুমাত্র সেই নির্দিষ্ট ক্লাসের ভেতরেই ব্যবহার করা যায়। ক্লাসের বাইরে বা কোনো চাইল্ড ক্লাসে এটি অ্যাক্সেস করা একেবারেই সম্ভব নয়। এটি মূলত সংবেদনশীল ডেটা সুরক্ষিত রাখতে ব্যবহৃত হয়।

৩. Protected (প্রোটেক্টেড):
এটি অনেকটা private এর মতোই কাজ করে। তবে মূল পার্থক্য হলো, protected প্রপার্টিগুলো ইনহেরিট করা চাইল্ড ক্লাসের (Subclass) ভেতর থেকে অ্যাক্সেস করা যায়। কিন্তু ক্লাসের বাইরের কোনো অবজেক্ট থেকে সরাসরি এটি ব্যবহার করা যায় না।

৪. Readonly (রিড-ওনলি):
readonly মডিফায়ার ব্যবহার করলে সেই প্রপার্টির মান শুধুমাত্র একবারই সেট করা যায় (সাধারণত কনস্ট্রাক্টর ফাংশনে)। একবার মান সেট হয়ে গেলে তা আর পরিবর্তন (modify) করা যায় না।

উদাহরণ (Code Example):

class Employee {
public name: string;
private salary: number;
protected department: string;
readonly id: number;

    constructor(id: number, name: string, salary: number, dept: string) {
        this.id = id;
        this.name = name;
        this.salary = salary;
        this.department = dept;
    }

    public getDetails() {
        return `${this.name} gets ${this.salary}`;
    }

}

class Manager extends Employee {
public showDepartment() {
// department অ্যাক্সেস করা যাবে কারণ এটি protected
return `Department is ${this.department}`;
}
}

const emp1 = new Employee(101, "Karim", 50000, "IT");
console.log(emp1.name); // Public: সঠিকভাবে কাজ করবে
console.log(emp1.id); // Readonly: মান দেখা যাবে, কিন্তু emp1.id = 102 লিখলে এরর আসবে
// console.log(emp1.salary); // Error: Private প্রপার্টি বাইরে থেকে অ্যাক্সেস করা যায় না

উপসংহার:
পরিশেষে বলা যায়, TypeScript এর Access Modifier গুলো আমাদের কোডকে আরও বেশি সুরক্ষিত, সুশৃঙ্খল এবং নির্ভরযোগ্য করে তোলে। সঠিক জায়গায় সঠিক মডিফায়ার ব্যবহারের মাধ্যমে একটি মজবুত ও ত্রুটিমুক্ত সফটওয়্যার আর্কিটেকচার তৈরি করা সহজ হয়।

বিঃদ্রঃ ইউটিউব, লিঙ্কডইন পোস্ট এবং 'প্রোগ্রামিং হিরো' (Programming Hero) এর ভিডিও দেখে আমি এই বিষয়গুলো শিখেছি এবং বুঝেছি। আমি নিজে যতটুকু বুঝতে পেরেছি, ঠিক ততটুকুই নিজের মতো করে লিখেছি। পরবর্তীতে লেখার গ্রামার ঠিক করতে এবং ফরম্যাট আরও সুন্দর করে সাজানোর জন্য এআই (AI) এর সাহায্য নিয়েছি। অর্থাৎ, মূল লেখা ও ধারণাগুলো সম্পূর্ণ আমার নিজের, তবে এটি গুছিয়ে উপস্থাপন করার কাজটি এআই-এর মাধ্যমে করা হয়েছে।
