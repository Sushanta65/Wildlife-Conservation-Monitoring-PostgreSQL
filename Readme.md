### Question 1: What is PostgreSQL? (PostgreSQL কী?)
Answer: PostgreSQL হলো একটি Relational Database Management System (RDBMS)। এতে আমরা তথ্য (Data) সংরক্ষণ করতে পারি, যেমন- ইউজারের নাম, ঠিকানা, প্রোডাক্টের দাম ইত্যাদি। PostgreSQL SQL আর JSON উভয়ই সাপোর্ট করে। এটা ব্যবহার করে আমরা সহজে তথ্য খুঁজে, যোগ করতে বা পরিবর্তন করতে পারি।

### Question 3: Explain the Primary Key and Foreign Key concepts in PostgreSQL. (Primary Key আর Foreign Key কী?): 
Answer: 
    Primary Key হলো এমন একটি জিনিস যেটা দিয়ে প্রতিটা তথ্য আলাদা করে চেনা যায়। যেমন: একজন রেঞ্জারের আইডি নম্বর একটি প্রাইমারি কি। 
    Foreign Key হলো অন্য টেবিলের Primary Key। এটা দিয়ে দুইটা টেবিলকে একসাথে সংযুক্ত করা যায়।

### Question 4: What is the difference between the VARCHAR and CHAR data types? (VARCHAR আর CHAR এর মধ্যে পার্থক্য কী?)
Answer: 
    CHAR: CHAR হলো fixed lenth ডেটা টাইপ। এখানে যতোটুকো length দেওয়া হবে সে ততটাই জায়গা নিয়ে নিবে, এমনকি যদি Length কমও হয়।
    VARCHAR: VARCHAR হলে যত অক্ষর বা Length দরকার ততটাই জায়গা নেয়, বাড়তি জায়গা নেয় না।

### Question 5: Explain the purpose of the WHERE clause in a SELECT statement. (SELECT-এ WHERE কেন ব্যবহার করি?)
Answer: Select এ Where ব্যবহার করি তখন, যখন আমাদের দরকার শুধু কিছু নির্দিষ্ট তথ্য। অর্থাৎ আমরা যখন কোন নির্দিষ্ট ডেটা বের করতে চাই তখন Select এর সাথে Where ব্যবহার করি। যেমন - 
  SELECT * FROM rangers WHERE name = 'Susanto';

 ### Question 8: What is the significance of the JOIN operation, and how does it work in PostgreSQL? (JOIN কী এবং কেন দরকার?)
Answer:  দিয়ে দুইটা টেবিলের তথ্য একসাথে দেখা যায়। যেমন, রেঞ্জার কোন কোন প্রানী দেখেছে সেটা জানতে হলে রেঞ্জার টেবিল আর সাইটিং টেবিল একসাথে JOIN করে দেখতে হয়। ধরি আমাদের দুইটা টেবিল আছে- 
rangers – এখানে রেঞ্জারের নাম, আইডি ইত্যাদি আছে।
zones – এখানে কোন রেঞ্জার কোন জোনে কাজ করে সেই তথ্য আছে।
এখন আমরা চাই, রেঞ্জারের নামের পাশে তার জোনের নামও দেখাতে।

    SELECT rangers.name, zones.zone_name
    FROM rangers
    JOIN zones ON rangers.id = zones.ranger_id;
    
এভাবেই আমরা JOIN ব্যবহার করি।
