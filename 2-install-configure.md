# ইন্সটলেশন এবং কনফিগারেশন

গিট নিয়ে কাজ শুরু করার জন্য আপনার কম্পিউটারকে গিট ব্যবহার উপযোগী করে নিতে হবে। সেজন্য আপনার কম্পিউটারে গিট ইন্সটল\(install\) করতে হবে। চলুন দেখে নেয়া যাক, কিভাবে গিট ইন্সটল এবং কনফিগার\(configure\) করে নিতে হয়।

## Windows:

১. গিট প্যাকেজটি ডাউনলোড করার জন্য এখানে [ক্লিক](http://git-scm.com/download/win) করুন।  
২. ডাউনলোড করা ফাইলটি ক্লিক করে ইন্সটল করে নিন।

## Linux:

Linux এর বিভিন্ন ডিস্ট্রো এর জন্য গিট ইন্সটল পদ্ধতি বিভিন্ন রকম। কিন্তু খুবই সহজ। ডিস্ট্রো অনুযায়ী terminal-এ নিচের কমান্ডগুলো লিখুন।

* Debian/Ubuntu  

  ```text
    # apt-get install git
  ```

* Fedora  

  ```text
    # yum install git
  ```

* Gentoo  

  ```text
    # emerge --ask --verbose dev-vcs/git
  ```

* Arch Linux  

  ```text
    # pacman -S git
  ```

* FreeBSD  

  ```text
    $ cd /usr/ports/devel/git
  ```

  ```text
    $make install
  ```

* Solaris 11 Express  

  ```text
    $ pkg install developer/versioning/git
  ```

* OpenBSD  

  ```text
    $ pkg_add git
  ```

## গিট কনফিগার

গিট কনফিগার করার মূল উদ্দেশ্য হচ্ছে, আপনি যখন গিট এর মাধ্যমে কমিট\(commit\) করবেন তখন কমিটের সাথে সে আপনার তথ্য সংরক্ষণ করে রাখবে। কনফিগারেশনের সময় আপনাকে শুধু আপনার user name এবং email address বলে দিতে হবে। Windows ব্যবহারকারীরা গিট ইন্সটল করার পর কম্পিউটার ডেক্সটপে gitBash নামে একটি শর্টকাট ফাইল তৈরি হবে। সেটি খুলে তাতে নিচের কমান্ডগুলো লিখুন। Linux ব্যবহারকারীরা terminal-এ কমান্ডগুলো লিখতে পারবেন।

```text
git config --global user.name "Your Name Here"
```

Your Name Here এর জায়গায় আপনার নাম লিখুন।

```text
git config --global user.email "your_email@youremail.com"
```

এখানে যে email address দিবেন তা অবশ্যই আপনার সার্ভার অ্যাকাউন্টের email address এর সাথে মিল থাকতে হবে। এখন আপনার কম্পিউটারটি গিট ব্যবহার উপযোগি হয়েছে। এখন থেকে আপনি আপনার কম্পিউটারে গিটের কমান্ডগুলো কাজে লাগাতে পারবেন। আমরা আমাদের সকল কমান্ড gitBash অথবা terminal-এ লিখবো।

`~/.gitconfig` ফাইল এ আপনার গ্লোবাল\(global\) কনফিগারেশন লেখা থাকে। আপনি যখন কোন একটি রিপোজিটরিতে `git init` কমান্ড দিবেন তখন `.git` নামের একটি ফোল্ডার তৈরি হবে। এই `.git` ফোল্ডারের ভিতরেই গিট সব তথ্য সংরক্ষিত রাখে।

আপনি কোন একটি রিপজিটরির জন্য গিটের গ্লোবাল কনফিগারেশনকে পরিবর্তন অথবা ওভাররাইট করতে পারেন। আপনি যদি কোন একটি রিপজিটরির জন্য `name` এবং `email` পরিবর্তন করতে চান তাহলে terminal দিয়ে রিপজিটরিতে গিয়ে নিচের কমান্ডগুলো দেন।

```text
git config --local user.name "Your Name Here"
git config --local user.email "your_email@youremail.com"
```

এখানে আপনি যে `নাম` এবং `ইমেইল` দিবেন তা শধুমাত্র এই রিপোজিটরির জন্য কনফিগার হবে। আপনার লোকাল কনফিগার `.git/config` ফাইল এ সংরক্ষিত হয়। Linux/Mac ব্যবহারকারীরা terminal-এ নিচের কমান্ড দিয়ে লোকাল কনফিগারেশন এর ফাইলটি দেখতে পারেন।

```text
nano .git/config
```

ফাইল এর শেষে যদি নিচের লাইনগুলো যোগ হয় তাহলে আপনার লোকাল কনফিগার সঠিকভাবে overwrite হয়েছে।

```text
[user]
        name = <your-name>
        email = <your-email>
```

আপনি নিচের কমান্ড দিয়ে আপনার গিট কনফিগারেশন একসাথে দেখতে পারবেন।

```text
git config --list
```

