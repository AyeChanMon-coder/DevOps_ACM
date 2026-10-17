## **Different type of merge strategies**

git မှာ merge strategies 4 မျိုးရှိပါတယ်။

fast-forward, non-fastforward, squash and merge, rebase and merge တို့ဖြစ်ပါတယ်။

1. fast-forward က target branch (eg, main branch) နဲ့ source branch (eg, feature branch) နဲ့က historyတူတဲ့ခါမျိုးမှာ merge လုပ်တဲ့ strategyဖြစ်ပါတယ်။ ဉပမာ။ main branch ကနေခွဲထွက်လာတဲ့ feature branch မှာ changes လုပ်ပြီး mainမှာ ဘာမှမလုပ်ပဲ no changes အခြေနေမှာ လာပေါင်းရင် သူ့ရဲ့ git graph က linear ဖြစ်ပြီး fast-forward strategy ဖြစ်ပါတယ်။

2. non fast-forward က target branch (eg, main branch) ကနေ source branch (eg, feature branch) ခွဲထားပြီးမှ mainမှာ changes တွေရှိနေပြီး feature branchမှာ mainရဲ့ new changesတွေက မရှိသေးဘူး။ အဲ့ဒီခါမှာ historyမတူတော့ဘူး။ အဲ့လိုချိန်မှာ mainကို merge လုပ်တဲ့ခါ main ထဲကို ပေါင်းလိုက်ရင် git က merge commit အသစ်တစ်ခုဖန်တီးပြီး ပေါင်းတယ်။ အဲ့ဒီခါ git graphက linear မဟုတ်တော့ပဲ non linear ပုံစံဖြစ်သွားတယ်။

3. linearဖြစ်ချင်ရင် rebase strategy သုံးလို့ရပါတယ်။ rebaseလုပ်လိုက်ရင် feature branchရဲ့ commit တွေကို main branch ရဲ့ထိပ်ဆုံးမှာ တစ်တန်းတည်းဖြစ်အောင် အသစ်ပြန်လည် တန်းစီပေးလိုက်တဲ့တွက် linear history ကို ရှင်းရှင်းလင်းလင်းဖြစ်စေတယ်။

4. squash and merge က feature branch မှာ ရှိသမျှ commitတွေကို commit တစ်ခုတည်းအဖြစ် အကုန် squashလိုက်ပြီးမှ main branchရဲ့ထိပ်ဆုံးမှာ commit အသစ်တစ်ခုအနေနဲ့ merge လုပ်လိုက်တဲ့ strategyဖြစ်ပါတယ်။

## **Cheatsheet for Git Branching**

1. git branch : local က branch အားလုံးကို ကြည့်ရှုခြင်းဖြစ်ပါတယ်။

2. git branch -a : local, remote (github/gitlab) မှာရဲ့ branchတွေအာလုံး ထုတ်ကြည့်တာဖြစ်ပါတယ်။

3. git branch: branch အသစ်တစ်ခုဖန်တီးခြင်း (အဲ့ဒီ branchထဲကိုတော့ ချက်ခြင်းဝင်မသွားသေးပါဘူး)

4. git switch/checkout: branch တစ်ခုခုဆီကိုပြောင်းရွေ့ဖို့ဖြစ်ပါတယ်။

5. git checkout -b / git switch -c : branch အသစ်ဆောက်ပြီး အဲ့ဒီ branchထဲကို ချက်ချင်းကူးပါတယ်။

6. git merge : သတ်မှတ်ထားတဲ့ branchက changesတွေကို လက်ရှိ target branchထဲ ပေါင်းထည့်ဖို့ဖြစ်ပါတယ်။

7. git pll origin : remote ပေါ်က updateတွေ local branchထဲယူလာပြီးပေါင်းချင်တဲ့ခါ သုံးပါတယ်။

8. git branch -d : မလိုတော့တဲ့ branchတွေ ဖျက်တဲ့ခါ သုံးတယ်။

## **Cheatsheet for time travel**

1. git log : commitတွေရဲ့ အသေးစိတ် record ကြည့်ဖို့သုံးတယ်။

2. git log --oneline: commit တစ်ခုချင်းစီကို တစ်ကြောင်းစီ အတိုချုံး ကြည့်ဖို့။

3. git log --graph --oneline --all: branchတွေခွဲထားပုံ၊ဘယ်လိုပေါင်းထားလဲဆိုတာ git graph ပုံစံကို မျဉ်းကြောင်းတွေနဲ့တူတူကြည့်ဖို့။

4. git reset --soft : သတ်မှတ်ထားတဲ့ commitဆီပြန်သွာတယ် ဒါပေမဲ့ ကိုယ်ရေးထားတဲ့ code changesတွေက staging area မှာ ဆက်ကျန်တယ်။

5. git reset --mixed (or) git reset : commit ရော staging ပါဖျက်ပစ်ပေမဲ့ local fileထဲမှာ codeကဆက်ရှိနေမယ်။

6. git reset --hard : အရင် commit တုန်းကတိုင်း အပြီးတိုင်ပြန်ပြောင်းပစ်တယ်။ ရေးထားတဲ့ codeအသစ်တွေအကုန်ပျောက်သွားတတ်လို့ သတိထားပြီးသုံးသင့်ပါတယ်။

7. git revert : တခြားသူတွေနဲ့ အလုပ်တူတူလုပ်တဲ့ခါ အရင် commitတစ်ခုခုမှာ errorတက်လို့ အဲ့ဒီ commitကိုတိုက်ရိုက်ဖျက်မပစ်ပဲ အဲ့ဒီအမှားကို ပြန်ပြင်တဲ့ commitအသစ်တခု ထပ်ဆောက်တယ်။ history က safe ဖြစ်လို့ သုံးရတာ အဆင်ပြေတယ်။
