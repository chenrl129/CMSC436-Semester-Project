# CMSC436-Semester-Project

Setting up User API Key:
1) Go to "https://beta.openai.com/account/api-keys" and create an API key - make sure to copy it. 
2) Go to MainActivity.ky and replace the following with your API key:
        return Request.Builder()
            .url("https://api.openai.com/v1/completions")
            .addHeader(
                "Authorization",
                "Bearer INSERT-API-KEY-HERE"
            )
3) Save and Run
