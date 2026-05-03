
<img align="right" width="150" src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-old-version-tutorial/join-slack-team.png">





প্রথম অবদান
<img alt="Git Bash" src="https://cdn.icon-icons.com/icons2/2699/PNG/512/git_scm_logo_icon_170096.png" width="200">	Git Bash সংস্করণ

প্রথমবার কিছু করা সবসময়ই কঠিন। বিশেষ করে যখন আপনি টিমে কাজ করেন, তখন ভুল করার ভয় থেকেই যায়। কিন্তু ওপেন সোর্স মানেই সহযোগিতা ও একসাথে কাজ করা।

আমরা নতুন ওপেন সোর্স অবদানকারীদের শেখা এবং তাদের প্রথম অবদান রাখার প্রক্রিয়াকে সহজ করতে চাই। আর্টিকেল পড়া বা ভিডিও দেখা সহায়ক হতে পারে, তবে বাস্তবে প্র্যাকটিস করার চেয়ে ভালো কিছু নেই।

এই প্রোজেক্টের উদ্দেশ্য হলো নতুনদের জন্য সহজবোধ্য গাইড তৈরি করা এবং তাদের প্রথম অবদান রাখার অভিজ্ঞতাকে আনন্দদায়ক করে তোলা। মনে রাখবেন: আপনি যত শান্ত ও আত্মবিশ্বাসী থাকবেন, শেখাও তত সহজ হবে।

যদি আপনার Windows মেশিনে Git Bash না থাকে, তবে এখান থেকে ইন্সটল করুন
।

<img align="right" width="300" src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-tutorial/fork.png" alt="এই রিপোজিটরিটি ফর্ক করুন" />
রিপোজিটরি Fork করুন

এই পেজের উপরের ডান দিকের Fork বাটনে ক্লিক করুন।
এতে করে আপনার অ্যাকাউন্টে রিপোজিটরিটির একটি কপি তৈরি হবে।

রিপোজিটরি Clone করুন

এখন আপনার ফর্ক করা রিপোজিটরিকে আপনার কম্পিউটারে ক্লোন করুন।

⚠️ গুরুত্বপূর্ণ: মূল রিপোজিটরি ক্লোন করবেন না। নিজের ফোর্ক থেকে ক্লোন করতে হবে।

১. "Code" বাটনে ক্লিক করুন এবং লিঙ্ক কপি করুন।

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-clone-1.png" alt="URL টি ক্লিপবোর্ডে কপি করুন" />

২. Git Bash ওপেন করুন। উইন্ডোজে এটি নিচের ছবির মতো দেখাবে:

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-terminal-1.png" alt="open git bash terminal" />

৩. প্রোজেক্ট রাখার ফোল্ডারে যান:

cd <folder>

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-terminal-2.png" alt="cd into a folder" />

৪. এখন কপি করা লিঙ্ক দিয়ে ক্লোন করুন:

git clone <repo-url>

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-clone-2.png" alt="এই রিপোজিটরিটি ক্লোন করুন" />

৫. ক্লোন করা ডিরেক্টরিতে যান এবং VS Code এ ওপেন করুন:

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-terminal-3.png" alt="cd into the newly cloned repo" />
একটি Branch তৈরি করুন

নতুন ব্রাঞ্চ তৈরি করুন এবং সেই ব্রাঞ্চে সুইচ করুন:

git checkout -b <branch-name>


👉 নাম দিন <add-your-name> ফরম্যাটে। যেমন:

add-james-smith

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-branch.png" alt="create a branch" />
পরিবর্তন করুন এবং Commit করুন

১. Contributors.md ফাইল ওপেন করুন।
২. নিচে স্ক্রল করে নিজের নাম যোগ করুন।
৩. ফাইল সেভ করুন।

উদাহরণ:

[James Smith](https://github.com/jamessmith)


পরিবর্তন চেক করতে:

git status

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-status.png" alt="গিট স্ট্যাটাস" />

পরিবর্তন স্টেজ করুন:

git add file-name


কমিট করুন:

git commit -m "Add your-name to Contributors list"


👉 এখানে <your-name> এর জায়গায় নিজের নাম লিখুন।

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-commit.png" alt="commit changes" />

কমিট লিস্ট চেক করতে:

git log --oneline

GitHub এ Push করুন

সব ধাপ শেষ হলে পরিবর্তনগুলো GitHub এ পাঠান:

git push origin <branch-name>

<img src="https://firstcontributions.github.io/assets/cli-tool-tutorials/git-bash-windows-tutorial/gb-push.png" alt="push changes" />
Pull Request পাঠান

GitHub এ আপনার রিপোজিটরিতে গিয়ে Compare & pull request বাটনে ক্লিক করুন।

<img src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-tutorial/compare-and-pull.png" alt="একটি পুল রিকোয়েস্ট তৈরি করুন" />

এরপর Pull Request সাবমিট করুন।

<img src="https://firstcontributions.github.io/assets/gui-tool-tutorials/github-desktop-tutorial/submit-pull-request.png" alt="পুল রিকোয়েস্ট জমা দিন" />

শীঘ্রই আপনার পরিবর্তনগুলো মূল প্রোজেক্টের প্রধান (main) ব্রাঞ্চে মার্জ হয়ে যাবে। পরিবর্তন মার্জ হলে ইমেইলে নোটিফিকেশন পাবেন।

এরপর কী করবেন?

অভিনন্দন 🎉 আপনি এখনই পুরো স্ট্যান্ডার্ড প্রক্রিয়া শেষ করলেন: fork → clone → edit → PR

👉 আপনার অবদান উদযাপন করুন এবং ওয়েব অ্যাপ
 থেকে বন্ধুদের সাথে শেয়ার করুন।

👉 যদি কোনো প্রশ্ন থাকে বা সাহায্য প্রয়োজন হয়, আমাদের Slack টিমে যোগ দিন: Slack টিমে যোগ দিন
।

অতিরিক্ত উপকরণ
অন্যান্য টুল ব্যবহার করে টিউটোরিয়াল

মূল পাতায় ফিরে যান