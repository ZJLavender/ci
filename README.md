[![Build Status](https://travis-ci.org/gopl/ci.svg?branch=master)](https://travis-ci.org/gopl/ci)
[![Coverage Status](https://coveralls.io/repos/github/gopl/ci/badge.svg)](https://coveralls.io/github/gopl/ci)


## 1 配置 Travis CI

* 添加 .travis.yml
```yaml
language: go
```

* 使用 GitHub 账号登陆 [Travis CI](https://travis-ci.org/)，获取 gopl 组织访问权限

* [添加仓库](https://travis-ci.org/profile/gopl)

	将 gopl/ci 设置为打开状态

* 设置 Build Status

	访问 [Travis 仓库](https://travis-ci.org/gopl/ci)，点击图标，选择 Markdown，复制、粘贴到 README.md 顶部


#### 参考资料

- 《GitHub 入门与实践》
- [Getting started](https://docs.travis-ci.com/user/getting-started/)
- [Building a Go Project](https://docs.travis-ci.com/user/languages/go)
- [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build/)



## 2 配置 Coveralls

* 修改 .travis.yml

```yaml
language: go
sudo: false
go:
  - 1.8.1
before_install:
  - go get github.com/mattn/goveralls
script:
  - goveralls -service=travis-ci
```

* 使用 GitHub 账号登陆 [Coveralls](https://coveralls.io/)，获取 gopl 组织访问权限

* [添加仓库](https://coveralls.io/repos/new)

	将 gopl/ci 设置为 ON 状态

* 设置 Coverage Status

	访问[仓库设置](https://coveralls.io/github/gopl/ci/settings)，点击状态图标后面的 EMBED 下拉框，选择 MARKDOWN，复制、粘贴到 READMED.md 顶部

* 设置覆盖率阈值

	可以设置[覆盖率阈值](https://coveralls.io/github/gopl/ci/settings)，当覆盖率小于某百分比，或覆盖率比上一次降低了多少百分比，就认为此次构建失败
	![](images/coverage_threshold.png)


#### 参考资料

- [goveralls](https://github.com/mattn/goveralls)
- [INSTRUCTIONS FOR USING TRAVIS](https://coveralls.zendesk.com/hc/en-us/articles/201342809-Go)

