成功安装NodeJS将同时安装NPM。为方便NodeJS版本管理，我们首先安装NVM(Node Version Manager)。

1. 安装NVM。

   ```bash
   brew install nvm
   ```

2. 按照提示在`.bash_profile`中添加NVM路径。

   ```bash
   export NVM_DIR="$HOME/.nvm"
   [ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm
   [ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
   ```

3. 用NVM安装NodeJS不同版本。

   ```
   nvm install stable #安装NodeJS最新版本
   nvm install 10 #安装NodeJS V10
   ```

4. 检查当前使用的NodeJS和NPM版本。

   ```
   node -v
   npm -v
   ```

5. node modules将被安装在这个路径下。

   ```
   /Users/xxxxx/.nvm/versions/node/v10.24.1/bin
   ```

   