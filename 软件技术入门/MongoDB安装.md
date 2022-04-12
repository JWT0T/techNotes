# MongoDB安装

1. 安装brew

   ````
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ````

2. 将brew加入命令行

   ```
   echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/jingyawang/.zprofile
   eval "$(/opt/homebrew/bin/brew shellenv)"
   ```

3. Download the official Homebrew formula for MongoDB and the Database Tools

   ```
   brew tap mongodb/brew
   ```

4. 安装MongoDB

   ```
   brew install mongodb-community@5.0
   ```

5. 启动mongod

   ```
   mongod --config /opt/homebrew/etc/mongod.conf
   ```