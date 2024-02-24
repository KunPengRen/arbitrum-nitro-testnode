FROM node:16

# 设置 Yarn 代理
ENV HTTP_PROXY=http://192.168.10.2:7890
ENV HTTPS_PROXY=http://192.168.10.2:7890

WORKDIR /workspace

# 拷贝 package.json 和 yarn.lock 文件
COPY ./package.json .
COPY ./yarn.lock .

# 执行 yarn 命令
RUN yarn

# 拷贝 TypeScript 文件和配置文件
COPY ./*.ts .
COPY ./tsconfig.json .

# 执行 TypeScript 编译
RUN yarn build

# 设置启动命令
ENTRYPOINT ["node", "index.js"]