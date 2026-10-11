> **停止维护：** clipboard_watcher 不再维护，后续剪贴板功能由
> [nativeapi-core](https://github.com/libnativeapi/nativeapi-core) 的 C++ `Clipboard` API 提供。
> Android C++ 实现需要原生宿主接入，并遵循系统剪贴板访问限制。
> 现有 Issues 和 PR 已作为停维工作的一部分关闭。

> **🚀 快速发布您的应用**: 试试 [Fastforge](https://fastforge.dev) - 构建、打包和分发您的 Flutter 应用最简单的方式。

# clipboard_watcher

[![pub version][pub-image]][pub-url] [![][discord-image]][discord-url] ![][visits-count-image] [![All Contributors][all-contributors-image]](#contributors)

[pub-image]: https://img.shields.io/pub/v/clipboard_watcher.svg
[pub-url]: https://pub.dev/packages/clipboard_watcher
[discord-image]: https://img.shields.io/discord/884679008049037342.svg
[discord-url]: https://discord.gg/zPa6EZ2jqb
[visits-count-image]: https://img.shields.io/badge/dynamic/json?label=Visits%20Count&query=value&url=https://api.countapi.xyz/hit/leanflutter.clipboard_watcher/visits
[all-contributors-image]: https://img.shields.io/github/all-contributors/leanflutter/clipboard_watcher?color=ee8449&style=flat-square

这个插件允许 Flutter 应用程序观察剪贴板的变化。

---

[English](./README.md) | 简体中文

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [平台支持](#%E5%B9%B3%E5%8F%B0%E6%94%AF%E6%8C%81)
- [快速开始](#%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B)
  - [安装](#%E5%AE%89%E8%A3%85)
  - [用法](#%E7%94%A8%E6%B3%95)
- [谁在用使用它？](#%E8%B0%81%E5%9C%A8%E7%94%A8%E4%BD%BF%E7%94%A8%E5%AE%83)
- [贡献者](#%E8%B4%A1%E7%8C%AE%E8%80%85)
- [许可证](#%E8%AE%B8%E5%8F%AF%E8%AF%81)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 平台支持

| 平台    | 支持                                                                   |
| ------- | :--------------------------------------------------------------------- |
| Linux   | ✔️ 完全支持                                                            |
| macOS   | ✔️ 完全支持                                                            |
| Windows | ✔️ 完全支持                                                            |
| iOS     | 14+ 需要用户权限才能读取从其他应用复制的数据<br>旧版本完全支持开箱即用 |
| Android | 10+ 仅当应用程序位于前台时有效<br>旧版本完全支持开箱即用               |

## 快速开始

### 安装

将此添加到你的软件包的 pubspec.yaml 文件：

```yaml
dependencies:
  clipboard_watcher: ^0.2.1
```

### 用法

```dart
class HomePage extends StatefulWidget {
  const HomePage({Key? key}) : super(key: key);

  @override
  _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> with ClipboardListener {
  @override
  void initState() {
    clipboardWatcher.addListener(this);
    // start watch
    clipboardWatcher.start();
    super.initState();
  }

  @override
  void dispose() {
    clipboardWatcher.removeListener(this);
    // stop watch
    clipboardWatcher.stop();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    // ...
  }

  @override
  void onClipboardChanged() async {
    ClipboardData? newClipboardData = await Clipboard.getData(Clipboard.kTextPlain);
    print(newClipboardData?.text ?? "");
  }
}
```

> 请看这个插件的示例应用，以了解完整的例子。

## 谁在用使用它？

- [比译](https://biyidev.com/) - 一个便捷的翻译和词典应用程序。

## 贡献者

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/lijy91"><img src="https://avatars.githubusercontent.com/u/3889523?v=4?s=100" width="100px;" alt="LiJianying"/><br /><sub><b>LiJianying</b></sub></a><br /><a href="https://github.com/leanflutter/clipboard_watcher/commits?author=lijy91" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/ademar111190"><img src="https://avatars.githubusercontent.com/u/1225438?v=4?s=100" width="100px;" alt="Ademar"/><br /><sub><b>Ademar</b></sub></a><br /><a href="https://github.com/leanflutter/clipboard_watcher/commits?author=ademar111190" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://customersuccessbox.com/"><img src="https://avatars.githubusercontent.com/u/64081899?v=4?s=100" width="100px;" alt="Amritpal Singh"/><br /><sub><b>Amritpal Singh</b></sub></a><br /><a href="https://github.com/leanflutter/clipboard_watcher/commits?author=boparaiamritcsb" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/jpnurmi"><img src="https://avatars.githubusercontent.com/u/140617?v=4?s=100" width="100px;" alt="J-P Nurmi"/><br /><sub><b>J-P Nurmi</b></sub></a><br /><a href="https://github.com/leanflutter/clipboard_watcher/commits?author=jpnurmi" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/Leobuaa"><img src="https://avatars.githubusercontent.com/u/6970283?v=4?s=100" width="100px;" alt="Leo Peng"/><br /><sub><b>Leo Peng</b></sub></a><br /><a href="https://github.com/leanflutter/clipboard_watcher/commits?author=Leobuaa" title="Code">💻</a></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td align="center" size="13px" colspan="7">
        <img src="https://raw.githubusercontent.com/all-contributors/all-contributors-cli/1b8533af435da9854653492b1327a23a4dbd0a10/assets/logo-small.svg">
          <a href="https://all-contributors.js.org/docs/en/bot/usage">Add your contributions</a>
        </img>
      </td>
    </tr>
  </tfoot>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

## 许可证

[MIT](./LICENSE)
