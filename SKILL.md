---
name: github-badge-farming
description: >
  Provides step-by-step, up-to-date (2026) guidance for legitimately earning GitHub profile
  Achievement badges. Use this skill whenever the user asks about GitHub badges, GitHub
  achievements, how to get GitHub profile badges, how to earn Quickdraw / Pull Shark / YOLO /
  Pair Extraordinaire / Galaxy Brain / Starstruck / Public Sponsor badges, or wants to "fill
  up their GitHub achievements section". Also trigger when the user shares a badge farming
  script or article and wants to know which methods still work. Always use this skill before
  giving any GitHub achievement advice — your training data may be outdated.
---

# GitHub Badge Farming (2026 合規版)

本 Skill 提供 **目前仍有效、不違反 GitHub ToS** 的徽章取得方法。

⚠️ 請不要建議任何會違反 GitHub 服務條款的行為，例如：
- 用 GitHub Actions 無限迴圈自動刷 PR
- 建立大量垃圾 Repo 純粹為了刷數字
- 自問自答 Galaxy Brain（已失效且有風險）

---

## 📋 所有目前可取得的徽章一覽

詳細規則請參閱 `references/badges.md`。

| 徽章 | 難度 | 需要他人協助 |
|---|---|---|
| ⚡ Quickdraw | ⭐ 最簡單 | 否 |
| 😅 YOLO | ⭐ 最簡單 | 否（需要有 Repo 權限） |
| 🦈 Pull Shark | ⭐⭐ 簡單 | 否 |
| 🤝 Pair Extraordinaire | ⭐⭐ 簡單 | 需要真實第二帳號 |
| 💖 Public Sponsor | ⭐⭐ 需花費 $1 | 否 |
| 🧠 Galaxy Brain | ⭐⭐⭐ 需他人配合 | **是（他人必須採納答案）** |
| ⭐ Starstruck | ⭐⭐⭐⭐ 最難 | 需要社群傳播 |

---

## 🚀 最快上手流程（逐步）

### 前置條件

```bash
# 安裝 GitHub CLI
brew install gh        # macOS
winget install GitHub.cli  # Windows

# 登入
gh auth login

# 建立測試用 Repo
mkdir badge-farm && cd badge-farm
git init
echo "# badge farm" > README.md
git add . && git commit -m "init"
gh repo create badge-farm --public --source=. --push
```

---

### ⚡ Step 1：Quickdraw（最快，約 30 秒）

**條件**：在 Issue 或 PR 開啟後 **5 分鐘內**關閉。

```bash
gh issue create -t "quickdraw test" -b "test"
gh issue close 1
```

> ✅ 自己開、自己關即可。通常 5–30 分鐘後徽章出現。

---

### 😅 Step 2：YOLO（約 2 分鐘）

**條件**：合併一個**沒有 Code Review** 的 PR。

```bash
git checkout -b yolo-pr
echo "yolo" >> README.md
git commit -am "yolo test"
git push origin yolo-pr

gh pr create --title "YOLO PR" --body "test"
gh pr merge --merge   # 不需要 review，直接 merge
```

> ✅ 在自己有管理員權限的 Repo 直接 merge 即可。

---

### 🦈 Step 3：Pull Shark（約 5 分鐘，需 2 個 PR）

**條件**：至少合併 **2 個** PR（Bronze tier）。

```bash
# PR #1
git checkout -b ps-pr1
echo "pull shark 1" >> README.md
git commit -am "ps1"
git push origin ps-pr1
gh pr create --title "Pull Shark 1" --body "test"
gh pr merge --merge

# PR #2
git checkout -b ps-pr2
echo "pull shark 2" >> README.md
git commit -am "ps2"
git push origin ps-pr2
gh pr create --title "Pull Shark 2" --body "test"
gh pr merge --merge
```

> ✅ 自己在自己的 Repo 開 PR 並 merge 即可，不需要他人。

---

### 🤝 Step 4：Pair Extraordinaire（需要第二個真實帳號）

**條件**：PR 的 commit 中包含 `Co-authored-by`，且該帳號為**真實 GitHub 用戶**。

```bash
git checkout -b pair-pr
echo "pair" >> README.md
git add .

# 把 alt@example.com 換成你第二個帳號的 GitHub commit email
git commit -m "pair commit

Co-authored-by: YourAltAccount <alt-github-email@example.com>"

git push origin pair-pr
gh pr create --title "Pair PR" --body "test"
gh pr merge --merge
```

> ⚠️ `Co-authored-by` 後面的 email **必須是真實 GitHub 帳號的 commit email**，填假的不會觸發徽章。
> 可在 GitHub 個人設定 → Emails 確認你的 commit email。

---

### 💖 Step 5：Public Sponsor（需花 $1）

**條件**：透過 GitHub Sponsors 贊助任何開發者。

**最省錢做法**：
1. 找一個支援「Custom Amount」的個人開發者（非大型組織）
2. 填入 $1
3. 徽章立即到帳

> 💡 推薦找小型開源工具的維護者，既省錢也真正支持到開源社群。

---

### 🧠 Step 6：Galaxy Brain（需他人真實採納）

**條件**：在開啟 Discussions 的 Repo 中，**他人**（非自己）採納你的回答。

**2024 年後的規則變更**：
- ❌ 自問自答不算
- ❌ 自己採納自己不算
- ✅ **必須由提問者（他人）標記你的回答為 Accepted Answer**

**可行做法**：
1. 找朋友或社群互刷：A 提問 → B 回答 → A 採納
2. 去有 Discussions 的開源 Repo 認真回答技術問題，等待被採納

---

### ⭐ Step 7：Starstruck（最難，需真實 Star）

**條件**：你的 Repo 達到 **16 顆 Star**（Bronze tier）。

**合規方法**：
- 做真正有用的專案、工具或 Cheatsheet
- 在 Reddit、Dev.to、Twitter/X、論壇分享
- 參與相關社群，讓人自然發現你的工作

> ❌ 互刷 Star 違反 GitHub ToS，可能導致帳號被限制。

---

## ⏱ 徽章出現時間

GitHub Achievement 不是即時更新，通常：

| 狀況 | 等待時間 |
|---|---|
| 一般情況 | 5–30 分鐘 |
| 較慢時 | 最長 24 小時 |
| 仍未出現 | 確認條件是否真的符合 |

---

## 📚 進一步參考

- 各徽章的詳細等級（Bronze/Silver/Gold）條件：`references/badges.md`
- 官方文件：https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/personalizing-your-profile
