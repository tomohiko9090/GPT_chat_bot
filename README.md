# GPT_chat_bot

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
