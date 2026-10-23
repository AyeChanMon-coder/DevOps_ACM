## **Cheatsheet for Git Branching**

နေ့စဉ်သုံး Git Branching အမိန့်များကို လွယ်ကူစွာ ကိုးကားနိုင်ရန် စုစည်းထားပါသည်။

| No. | Command | Description |
| :---: | :--- | :--- |
| 1 | `git branch` | local က branch အားလုံးကို ကြည့်ရှုခြင်းဖြစ်ပါတယ်။ |
| 2 | `git branch -a` | local, remote (github/gitlab) မှာရဲ့ branchတွေအာလုံး ထုတ်ကြည့်တာဖြစ်ပါတယ်။ |
| 3 | `git branch <branch-name>` | branch အသစ်တစ်ခုဖန်တီးခြင်း (အဲ့ဒီ branchထဲကိုတော့ ချက်ချင်းဝင်မသွားသေးပါဘူး) |
| 4 | `git switch` / `git checkout` | branch တစ်ခုခုဆီကိုပြောင်းရွေ့ဖို့ဖြစ်ပါတယ်။ |
| 5 | `git checkout -b` / `git switch -c` | branch အသစ်ဆောက်ပြီး အဲ့ဒီ branchထဲကို ချက်ချင်းကူးပါတယ်။ |
| 6 | `git merge` | သတ်မှတ်ထားတဲ့ branchက changesတွေကို လက်ရှိ target branchထဲ ပေါင်းထည့်ဖို့ဖြစ်ပါတယ်။ |
| 7 | `git pull origin` | remote ပေါ်က updateတွေ local branchထဲယူလာပြီးပေါင်းချင်တဲ့ခါ သုံးပါတယ်။ |
| 8 | `git branch -d` | မလိုတော့တဲ့ branchတွေ ဖျက်တဲ့ခါ သုံးတယ်။ |