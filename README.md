# 文件摘要

概述個人用 Oh-My-Zsh 的安裝及設定作業程序。

**作業環境：**

  - 作業系統： OS X V10.11.3
  - iTerm2： Build 2.1.4
  - ZSH： V5.0.7 (x86_64-apple-darwin15.2.0)

## 安裝及設定作業程序

**程序步驟：**

 1. 安裝 Oh-My-Zsh
 2. 安裝 Powerline Fonts
 3. 安裝 iTerm2
 4. 設定 iTerm2 使用的 Profile
 5. 複製 Theme 檔案到 Oh-My-Zsh 安裝的目錄路徑
 6. 修改 Oh-My-Zsh 的設定檔「.zshrc」

### 1. 安裝 Oh-My-Zsh

請參考**[這篇文件](http://sourabhbajaj.com/mac-setup/iTerm/zsh.html)**，進行「ZSH」、「oh-my-zsh」安裝作業；及「Default Shell」變更作業。


    (1) 使用 homebrew 完成「ZSH」安裝：

        ```
        brew install zsh zsh-completions
        ```

    (2) 使用 curl 完成「oh-my-zsh」安裝

        ```
        curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
        ```

    (3) 使用「終端機」執行下列指令，完成「Default Shell」變更

        ```
        chsh -s /bin/zsh
        ```

### 2. 安裝 Powerline Fonts

因後續的「終端機 Prompt」設定，會用到**特殊字型：**「Meslo LG S DZ Regular for Powerline」。

所以請用「git clone」指令，自**[網址：https://github.com/powerline/fonts](https://github.com/powerline/fonts)** 下載字型檔，並依據其「ReadMe 文件」之說明，完成 Powerline Fonts 的安裝。

### 3. 安裝 iTerm2

下載及安裝 iTerm2 軟體。

  (1) 自 iTerm2 官網：[http://www.iterm2.com](http://www.iterm2.com)，下載軟體。

  (2) 安裝 iTerm2 軟體。

### 4. 設定 iTerm2 使用的 Profile

    (1) 下載終端機的 Color Scheme：「Solarized dark iterm colors」

    (2) 透過 iTerm2 的 Preferences 功能，完成「Colors 設定」

        a. 下載「Solarized dark iterm colors」色彩設定

        b. 執行「iTerm / Preference...」功能

        c. 切換到「 Profiles / Default / Colors」面板

        d. 執行「Load Presets... / Import....」功能，匯入「Solarized dark iterm colors」

    (3) 透過 iTerm2 的 Preferences 功能，完成「Text 設定」

        a. 執行「iTerm / Preference...」功能

        b. 切換到「 Profiles / Default / Text」面板

        c. 在「Regular Font」，透過「Change Font」按鈕，將「Font」變更成「Meslo LG S Regular for Powerline」

        d. 在「Non-ASCII Font」，透過「Change Font」按鈕，將「Font」變更成「Meslo LG S Regular for Powerline」

### 5. 複製 Theme 檔案到 Oh-My-Zsh 安裝的目錄路徑

複製**檔案**：「ccc.zsh-theme」，放到**目錄路徑**：「~/.oh-my-zsh/themes/」處。

與「終端機 Prompt」相關的**關鍵設定**，請參考檔案：「ccc.zsh-theme」，在「行號」： **114 ~ 116** 及 **129 ~ 130** 這兩段的內容。

```
114 prompt_2nd_line() {
115   echo "\u26a1"
116 }
117
118 ## Main prompt
119 build_prompt() {
120   RETVAL=$?
121   prompt_status
122   prompt_context
123   prompt_dir
124   prompt_git
125   prompt_end
126   # prompt_2nd_line
127 }
128
129 PROMPT='%{%f%b%k%}$(build_prompt)
130 $(prompt_2nd_line) [$(date +%H:%M:%S)]: '

```

### 6. 修改 Oh-My-Zsh 的設定檔「.zshrc」

  (1) 使用「文字編輯器（Editor）」修改**~/.zshrc**檔案。

  (2) 參考下列內容，變更「ZSH_THEME」的設定。

     ```
     ZSH_THEME="ccc"
     ```
