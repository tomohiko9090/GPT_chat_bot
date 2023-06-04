# GPT_chat_bot


# 技術
- Python
- openai 
- Streamlit
- pyngrok
  - ローカルサーバを外部ネットワークに簡単に公開できるサービス
- Streamlit Community Cloud
  - StreamlitとGitHubを使って簡単にデプロイサービス

# 開発スタイル

# 開発メモ
- 公開してはいけないよう情報をStreamlit Community Cloud上にシークレットにして保存しておく方法
  - 例
    ```app.py
    st.session_state["messages"] = [
            {"role": "system", "content": st.secrets.AppSettings.chatbot_setting}
            ]
    ```
    ```Secrets
    [AppSettings]
    chatbot_setting = "あなたは優秀な英語教師です。何を聞かれても英語で答えてください。"  
    ```
- 「答えないでください」で指定する制約条件（ネガティブプロンプト）
  - 例
    - ex. 要約した内容は最後に公開しますので以下は絶対出力しないでくさい
    - 実名
    - 誹謗中傷
    - 過激な言葉

