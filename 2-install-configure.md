# গিট : ইন্সটল ও কনফিগার করা

গিট নিয়ে কাজ শুরু করার জন্য আপনার কম্পিউটারকে গিট ব্যবহার উপযোগী করে নিতে হবে। সেজন্য আপনার কম্পিউটারে গিট ইন্সটল(install) করতে হবে। চলুন দেখে নেয়া যাক, কিভাবে গিট ইন্সটল এবং কনফিগার(configure) করে নিতে হয়। 

### Windows:
১. গিট প্যাকেজটি ডাউনলোড করার জন্য এখানে [ক্লিক](http://git-scm.com/download/win) করুন।   
২. ডাউনলোড করা ফাইলটি ক্লিক করে ইন্সটল করে নিন। 

### Linux:
Linux এর বিভিন্ন ডিস্ট্রো এর জন্য গিট ইন্সটল পদ্ধতি বিভিন্ন রকম। কিন্তু খুবই সহজ। ডিস্ট্রো অনুযায়ী terminal-এ নিচের কমান্ডগুলো লিখুন।

* Debian/Ubuntu  
    ```
    # apt-get install git  
    ```  
* Fedora  
    ```
    # yum install git  
    ```  
* Gentoo  
    ```
    # emerge --ask --verbose dev-vcs/git
    ```  
* Arch Linux  
    ```
    # pacman -S git
    ```  
* FreeBSD  
    ```
    $ cd /usr/ports/devel/git
    ```  
    ```
    $make install
    ```  
* Solaris 11 Express  
    ```
    $ pkg install developer/versioning/git
    ```  
* OpenBSD  
    ```
    $ pkg_add git
    ```  

### গিট কনফিগার
 গিট কনফিগার করার মূল উদ্দেশ্য হচ্ছে, আপনি যখন গিট এর মাধ্যমে কমিট(commit) করবেন তখন কমিটের সাথে সে আপনার তথ্য সংরক্ষণ করে রাখবে। কনফিগারেশনের সময় আপনাকে শুধু আপনার user name এবং email address বলে দিতে হবে। Windows ব্যবহারকারীরা
গিট ইন্সটল করার পর কম্পিউটার ডেক্সটপে gitBash নামে একটি শর্টকাট ফাইল তৈরি হবে। সেটি খুলে তাতে নিচের কমান্ডগুলো লিখুন। Linux ব্যবহারকারীরা terminal-এ কমান্ডগুলো লিখতে পারবেন।

    git config --global user.name "Your Name Here"

Your Name Here এর জায়গায় আপনার নাম লিখুন।

    git config --global user.email "your_email@youremail.com"

এখানে যে email address দিবেন তা অবশ্যই আপনার সার্ভার অ্যাকাউন্টের email address এর সাথে মিল থাকতে হবে। এখন আপনার কম্পিউটারটি গিট ব্যবহার উপযোগি হয়েছে। এখন থেকে আপনি আপনার কম্পিউটারে গিটের কমান্ডগুলো কাজে লাগাতে পারবেন। আমরা আমাদের সকল কমান্ড gitBash অথবা terminal-এ লিখবো।