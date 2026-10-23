## **Different type of merge strategies**

git မှာ merge strategies 4 မျိုးရှိပါတယ်။

fast-forward, non-fastforward, squash and merge, rebase and merge တို့ဖြစ်ပါတယ်။

---

### 1. Fast-Forward
fast-forward က target branch (eg, main branch) နဲ့ source branch (eg, feature branch) နဲ့က historyတူတဲ့ခါမျိုးမှာ merge လုပ်တဲ့ strategyဖြစ်ပါတယ်။ ဉပမာ။ main branch ကနေခွဲထွက်လာတဲ့ feature branch မှာ changes လုပ်ပြီး mainမှာ ဘာမှမလုပ်ပဲ no changes အခြေနေမှာ လာပေါင်းရင် သူ့ရဲ့ git graph က linear ဖြစ်ပြီး fast-forward strategy ဖြစ်ပါတယ်။

**Visual Diagram:**

Before Merge:
```text
A --- B (main)
       \
        C --- D (feature)
```
```text
After Fast-Forward Merge (on main):
A --- B --- C --- D (main & feature)
```
### 2. Non Fast-Forward
non fast-forward က target branch (eg, main branch) ကနေ source branch (eg, feature branch) ခွဲထားပြီးမှ mainမှာ changes တွေရှိနေပြီး feature branchမှာ mainရဲ့ new changesတွေက မရှိသေးဘူး။ အဲ့ဒီခါမှာ historyမတူတော့ဘူး။ အဲ့လိုချိန်မှာ mainကို merge လုပ်တဲ့ခါ main ထဲကို ပေါင်းလိုက်ရင် git က merge commit အသစ်တစ်ခုဖန်တီးပြီး ပေါင်းတယ်။ အဲ့ဒီခါ git graphက linear မဟုတ်တော့ပဲ non linear ပုံစံဖြစ်သွားတယ်။

**Visual Diagram:**
Before Merge:
```text
A --- B --- C (main)
       \
        D --- E (feature)
```
```text
After Non-Fast-Forward Merge (on main):
A --- B --- C ------- M (main - Merge Commit)
       \            /
        D --- E --- (feature)
```

### 3. Rebase
linearဖြစ်ချင်ရင် rebase strategy သုံးလို့ရပါတယ်။ rebaseလုပ်လိုက်ရင် feature branchရဲ့ commit တွေကို main branch ရဲ့ထိပ်ဆုံးမှာ တစ်တန်းတည်းဖြစ်အောင် အသစ်ပြန်လည် တန်းစီပေးလိုက်တဲ့တွက် linear history ကို ရှင်းရှင်းလင်းလင်းဖြစ်စေတယ်။

**Visual Diagram:**
Before Rebase:
```text
A --- B --- C (main)
       \
        D --- E (feature)
```
After Rebase (on feature):
```text
A --- B --- C (main)
             \
              D' --- E' (feature - Rebased)
```

### 4. Squash and merge
squash and merge က feature branch မှာ ရှိသမျှ commitတွေကို commit တစ်ခုတည်းအဖြစ် အကုန် squashလိုက်ပြီးမှ main branchရဲ့ထိပ်ဆုံးမှာ commit အသစ်တစ်ခုအနေနဲ့ merge လုပ်လိုက်တဲ့ strategyဖြစ်ပါတယ်။

**Visual Diagram:**
Before Squash and Merge:
```text
A --- B (main)
       \
        C --- D --- E (feature - multiple commits)
```
```text
After Squash and Merge (on main):
A --- B --- CDE (main - Single Squashed Commit)
```

### 5.Git Merge vs Git Rebase: Detailed Comparison
Git တွင် Branch နှစ်ခုကို ပေါင်းစပ်ရာ၌ အသုံးအများဆုံး နည်းလမ်း (၂) ခုဖြစ်ပြီး ၎င်းတို့၏ အဓိက ကွာခြားချက်မှာ Commit History ကို ကိုင်တွယ်ပုံ ပေါ်တွင် မူတည်နေပါသည်။

| အချက်အလက် | Git Merge | Git Rebase |
| :--- | :--- | :--- |
| **Commit History** | Non-linear (Branching များကို အမှန်အတိုင်း အသေးစိတ်ပြသသည်) | Linear (သပ်ရပ်ရှင်းလင်းပြီး တစ်န်းတည်းဖြစ်သော history ကို ထွက်စေသည်) |
| **Merge Commit** | Merge Commit အသစ် (M) တစ်ခု ထပ်ပေါ်လာသည် | Merge Commit မပါရှိပါ (History ကို အသစ်ပြန်လည် တန်းစီသည်) |
| **Safety (လုံခြုံမှု)** | အလွန်လုံခြုံသည် (Team များနှင့် အလုပ်လုပ်ရာတွင် History မပျက်စေရန် အသင့်တော်ဆုံး) | History ကို ပြန်လည်ရေးသားခြင်း (Rewriting) ဖြစ်သောကြောင့် Shared/Public Branch တွင် သတိထားသုံးရသည် |
| **အဓိက အသုံးဝင်ပုံ** | Branch ပေါင်းစပ်ထားမှုကို အမှန်အတိုင်း အသေးစိတ် မှတ်တမ်းတင်လိုသည့်အခါ | History ကို ရှုပ်ထွေးမှုမရှိဘဲ ရှင်းရှင်းလင်းလင်း Linear ဖြစ်စေလိုသည့်အခါ |