
<img align="right" width="150" src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-old-version-tutorial/join-slack-team.png">



প্রথম অবদান (First Contribution)
<img alt="Git Bash" src="https://cdn.icon-icons.com/icons2/2699/PNG/512/git_scm_logo_icon_170096.png" width="200">	Git Bash সংস্করণ

প্রথমবার কিছু করলে সেটা কঠিন মনে হয়। বিশেষ করে যখন সহযোগিতামূলক কাজ হয়, তখন ভুল করার ভয় থাকে। কিন্তু ওপেন সোর্স মানেই সহযোগিতা – একসাথে কাজ করা।

আমরা চেয়েছি নতুন ওপেন সোর্স অবদানকারীদের জন্য শেখার পথ সহজ করা। শুধু টিউটোরিয়াল পড়ে বা ভিডিও দেখে নয় – বরং হাতে কলমে প্র্যাকটিস করে শিখলে অনেক দ্রুত বোঝা যায়। এই প্রোজেক্টের উদ্দেশ্য হলো নতুনদের গাইড করা এবং তাদের প্রথম অবদান রাখার অভিজ্ঞতাকে সহজ করা।

মনে রাখবেন, আপনি যত বেশি স্বাচ্ছন্দ্যবোধ করবেন, শেখাও তত ভালো হবে।

যদি আপনি উইন্ডোজ ব্যবহার করেন এবং আপনার কাছে Git Bash না থাকে, এখান থেকে ইন্সটল করুন
।

<img align="right" width="300" src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-tutorial/fork.png" alt="এই রিপোজিটরিটি ফর্ক করুন" />
এই রিপোজিটরিকে Fork করুন

এই পেজের উপরের ডান দিকে থাকা Fork বাটনে ক্লিক করুন।
এতে করে আপনার গিটহাব অ্যাকাউন্টে এই রিপোজিটরির একটি কপি তৈরি হবে।

রিপোজিটরি ক্লোন করুন

এবার আপনার ফোর্ক করা রিপোজিটরিটি নিজের কম্পিউটারে ক্লোন করুন।

⚠️ খেয়াল রাখবেন: মূল রিপোজিটরি ক্লোন করবেন না, বরং নিজের ফোর্ক থেকে ক্লোন করতে হবে।

১. আপনার রিপোজিটরির পেজে যান, "Code" বাটনে ক্লিক করুন এবং সেখানে দেওয়া লিঙ্ক কপি করুন।

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-clone-1.png" alt="URL টি ক্লিপবোর্ডে কপি করুন" />

২. Git Bash অ্যাপ্লিকেশন খুলুন। উইন্ডোজে এটি নিচের ছবির মতো দেখাবে:

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-terminal-1.png" alt="open git bash terminal" />

৩. সেই ফোল্ডারে যান যেখানে আপনি প্রোজেক্টটি রাখতে চান:

cd <folder>

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-terminal-2.png" alt="cd into a folder" />

৪. এবার রিপোজিটরিটি ক্লোন করুন:

git clone <repo-url>

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-clone-2.png" alt="এই রিপোজিটরিটি ক্লোন করুন" />

৫. ক্লোন করা ডিরেক্টরিতে যান এবং Visual Studio Code এ ওপেন করুন:

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-terminal-3.png" alt="cd into the newly cloned repo" />
একটি নতুন ব্রাঞ্চ তৈরি করুন

নিচের কমান্ড ব্যবহার করে একটি নতুন ব্রাঞ্চ তৈরি করুন এবং সেই ব্রাঞ্চে চলে যান:

git checkout -b <branch-name>


👉 আপনার ব্রাঞ্চের নাম দিন <add-your-name>। যেমন:

add-james-smith

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-branch.png" alt="create a branch" />
পরিবর্তন করুন এবং Commit করুন

১. Contributors.md ফাইল ওপেন করুন।
২. নিচের দিকে স্ক্রল করুন এবং সেখানে আপনার নাম যোগ করুন।
৩. ফাইলটি সেভ করুন।

উদাহরণ:

[James Smith](https://github.com/jamessmith)


পরিবর্তন হয়েছে কিনা দেখতে:

git status

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-status.png" alt="গিট স্ট্যাটাস" />

ফাইল স্টেজ করতে:

git add file-name


কমিট করতে:

git commit -m "Add your-name to Contributors list"


👉 <your-name> এর জায়গায় নিজের নাম লিখবেন।

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-commit.png" alt="commit changes" />

কমিট চেক করতে চাইলে:

git log --oneline

পরিবর্তন GitHub এ Push করুন

সব ধাপ শেষ হলে পরিবর্তনগুলো GitHub এ পাঠাতে হবে:

git push origin <branch-name>

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-push.png" alt="push changes" />
Pull Request পাঠান

GitHub এ আপনার রিপোজিটরিতে গেলে Compare & pull request বাটন দেখতে পাবেন। সেখানে ক্লিক করুন।

<img src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-tutorial/compare-and-pull.png" alt="একটি পুল রিকোয়েস্ট তৈরি করুন" />

এরপর Pull Request সাবমিট করুন।

<img src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-tutorial/submit-pull-request.png" alt="পুল রিকোয়েস্ট জমা দিন" />

শীঘ্রই আপনার পরিবর্তনগুলো মূল রিপোজিটরির main ব্রাঞ্চে মার্জ হয়ে যাবে। পরিবর্তন মার্জ হলে ইমেইলে নোটিফিকেশন পাবেন।

এরপর কী করবেন?

অভিনন্দন 🎉 আপনি এখনই সাধারণ fork → clone → edit → PR ওয়ার্কফ্লো সম্পন্ন করলেন, যা একজন অবদানকারী হিসেবে বারবার ব্যবহার করতে হবে।

👉 আপনার অবদান উদযাপন করুন এবং ওয়েব অ্যাপ
 থেকে বন্ধুদের সাথে শেয়ার করুন।

👉 কোনো প্রশ্ন থাকলে বা সাহায্যের প্রয়োজন হলে আমাদের Slack টিমে যোগ দিতে পারেন: স্ল্যাক টিমে যোগ দিন
।

অতিরিক্ত উপকরণ
অন্য টুল ব্যবহার করে টিউটোরিয়াল

মূল পাতায় ফিরে যান