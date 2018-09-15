# গিট ব্রাঞ্চ

১টা ছোট্ট গল্প দিয়ে শুরু করি। কোন প্রোজেক্ট করতে গিয়ে কিছু কোড লিখে রান দিলাম, কোড কাজ করে। তখন ১টা ব্যাকআপ রাখার জন্য প্রজেক্ট ফোল্ডার জিপ করে আবার আমরা  কোড লেখা শুরু করি। কিন্তু এবার কোড রান দিলে error দেখায়। কথায় ভুল হইসে অনেক সময় ঠিক করা যায় না, তখন প্রোজেক্ট ফলদাত ডিলিট করে ব্যাকআপ জিপ-কে আন-জিপ করে আবার কাজ করি। 
এই যে গল্প বললাম, এটাই গিট ব্রাঞ্চ এর কাজ। এবার আসি কিভাবে ব্রাঞ্চ কাজ করে।

প্রথমেই ১টা প্রোজেক্ট দরকার। ধরি git-branch-demo আমাদের প্রজেক্ট। Terminal খুলে টাইপ করুন ঃ 

```
mkdir git-branch-demo
cd git-branch-demo  
git init    # initiate empty local repo
echo " # inside master branch " >> main.cpp
```

By default এটা আমাদের মুল ব্রাঞ্চ, এর নাম master. আমরা নতুন ব্রাঞ্চ তোইরই করব এভাবেঃ 

```
git checkout -b develop
```

আমরা ব্রাঞ্চ চেক করতে পারি 
```git branch```

আউটপুট
```
*develop
 master
```
১ ব্রাঞ্চ থেকে অন্য়টায় যেতে হয় ঃ
``` 
git checkout <brunch-name>
# such as

git checkout master # to switch to master

git checkout develop # to switch to develop
```
আমরা ডেভেলপ ব্রাঞ্চ এ যাই । ১টা নতুন ফাইল বানাই ঃ 
```
touch branch1.cpp

```
এবার সেখানে নতুন কিছু কোড লিখি। যেমন ঃ
```
\**
*   inside develop branch:   branch1.cpp 
*\ 
#include <stdio.h>
int main()
{
    printf("Hello Branch 1 on develop\n");
    return 0;
}
```
এই ব্রাঞ্চ এর কাজ শেষ হলে কমিট করি ঃ 
```
git add .
git status
git commit -m "FC dev 2018-09-15 1"
```
আমাদের আপাতত এই ব্রাঞ্চ এর কাজ শেষ। কাজেই মাস্টের ব্রাঞ্চ এ ফিরে যাই ঃ 
```
git checkout master
```
এবার আপনার ফোল্ডারটি ১বার দেখুন। branch1.cpp নাই! ভয়ের কিছু নাই, develop ব্রাঞ্চ এ ফিরে গেলেই আবার চলে আসবে! নিজে চেষ্টা করে দেখুন! 

যাহোক, এবার মাস্টার ব্রাঞ্চ এ কিছু কোড লিখি। তবে খেয়াল রাখতে হবে, অন্য ব্রাঞ্চ এ যে ফাইল এ কোড লিখা হইসে ( এক্ষেত্রে branch1.cpp ), সেই নামের ফাইলে কিছু লিখবেন না, অন্যথায় পরবর্তীরে সমস্যা হবে (merge conflict) । এই টিউটোরিয়াল সহজ রাখতে merge conflict আপাতত বাদ। 
ফিরে আসি কোডে। 
master ব্রাঞ্চের main.cpp ফাইলে কিছু কোড লিখি ঃ 
``` 
#include <stdio.h>
int main()
{
    printf("Hello master branch\n");
    return 0;
}
```
এবার আগের মতো কমিট করি ঃ 
```
git add .
git status
git commit -m "FC master 2018-09-15 1"
```

এবার আমরা merge করব, অর্থাৎ ২টো ব্রাঞ্চকে মিলিয়ে দিব ।  এজন্য কমান্ড ঃ 

```
git merge <branch-name>
```
যে ব্রাঞ্চে merge করব, সেই ব্রাঞ্চ এ যাবো (এক্ষেত্রে  master ) এবং যে ব্রাঞ্চকে মারজ করবো তার নাম কমান্ড এ দিবো ( এক্ষেত্রে  ) । সুতরাং আমরা master এ গিয়ে টার্মিনালে লিখব ঃ 
```
git merge develop
```

তাহলে master ব্রাঞ্চে দিন শেষে আমাদের সম্পূর্ণ প্রোজেক্ট তৈরি হয়ে গেলো, যাতে main.cpp, branch1.cpp এবং তাদের কোড সবকিছু আছে। এরকম একাধিক ব্রাঞ্চ থাকলে সবাইকে মারজ করা যাবে। 
আমরা github ইতাদি-তেও আমাদের ব্রাঞ্চ রাখতে পারি। ৪ নং অধ্যায় এ রিমোট রিপো বানানোর নিয়ম আছে। সেগুলার পর
এই কমান্ড ব্যবহার করুন ঃ 

``` 
git push -u origin master   # to push master branch

git push -u origin develop  # to push develop branch
```

আশা করি ব্রাঞ্চের ব্যপারটা পরিষ্কার হয়ে গেছে! 