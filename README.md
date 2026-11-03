# Tibo 風格大頭照

一個 Codex skill：以本人照片作為身分來源，參考內建 Tibo 圖片的人物位置、臉部朝向、姿勢、表情和拍攝感，製作寫實大頭照。

![Tibo 姿勢參考圖](assets/tibo-reference.png)

## 特色

- 保留本人五官、髮型、膚色與可辨識特徵，並分別比對人物位置、臉部轉向與俯仰、歪頭、身體朝向及頭頸肩關係。
- 參考自然露齒笑、黑色圓領上衣與暖色背景；預設為 1:1 正方形照片，滿版且不加圓框。
- 依照片內區比對頭頂、眼睛、下巴、領口與肩膀位置，避免自動置中或放大胸肩。
- 已認可成品可針對身體位置或指定角度局部調整，盡量保留其他已認可的細節。
- 內建原始參考圖、放大檢視圖、中文提示詞與成品核對項目。

## 安裝

從 [Releases](https://github.com/irons163/tibo-avatar/releases/latest) 下載 `tibo-avatar-v*.zip`，解壓後將其中的 `tibo-avatar` 資料夾放入 Codex 的 skills 目錄（預設為 `~/.codex/skills/`）。如果已設定 `CODEX_HOME`，則放入 `$CODEX_HOME/skills/`。若已有同名資料夾，請先備份或自行確認是否取代。

安裝後的結構如下：

```text
skills/
└── tibo-avatar/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── assets/
        ├── tibo-reference.png
        └── tibo-reference-detail.png
```

安裝方式可參考 [OpenAI 的 Codex skill 範例](https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex)。

## 使用

在可使用圖片編輯功能的 Codex 工作階段提供本人照片，並輸入：

```text
請用 $tibo-avatar，保留我的五官，依 Tibo 原圖的人物與身體位置、臉部轉向與俯仰、歪頭及頭頸肩姿勢修這張照片；匹配黑衣、背景與笑容，不加圓框。
```

若照片中有多人，請說明要修哪一位。需要圓形裁切或透明背景時，可在要求中明確指定。圖片編輯功能不可用時，skill 會提供提示詞，無法直接產生成品。

## 專案內容

- [SKILL.md](SKILL.md)：完整修圖流程、提示詞與核對條件。
- [agents/openai.yaml](agents/openai.yaml)：Codex 介面顯示名稱與預設提示詞。
- [assets/](assets/)：姿勢參考原圖與等比例放大圖。

圖片生成結果可能與範例有差異；可依臉部角度、歪頭或頭肩關係提出具體修正。
