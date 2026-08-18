# NiuLai-image

一个用于生成低成本早期 3D CGI 图像的 Codex Skill：低面数角色、僵硬绑定、低分辨率重复贴图、素材包式山林，以及 PS2 游戏过场／儿童 VCD 的粗糙数字质感。

## 特点

- 使用 MusePool StyleSpec v1 保存结构化风格规则。
- 支持 10 个 Cookbook 基础变量和 4 个 NiuLai 扩展变量。
- 强制可见低面数切面、8–12 边圆柱和突兀关节，不用圆润高模冒充复古。
- 强制 32–128 px 重复漫反射贴图、像素块、接缝、UV 拉伸和有限纹理过滤。
- StyleSpec 自包含全部视觉规则，仓库不附带参考图片。

## 安装

```bash
git clone https://github.com/yusen-dev/NiuLai-image.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R NiuLai-image/skills/niulai-low-fi-cgi \
  "${CODEX_HOME:-$HOME/.codex}/skills/niulai-low-fi-cgi"
```

重新启动 Codex，或刷新 Skill 列表后即可使用。

## 使用示例

```text
使用 $niulai-low-fi-cgi，生成一张三个萝卜工人在低模森林公交站等待末班车的 4:3 儿童 VCD 动画截图。
```

也可以提供一张待转换图片，并要求保留主体、构图和文字，仅迁移 NiuLai 的低模与低清贴图系统。

## 仓库结构

```text
skills/niulai-low-fi-cgi/
├── SKILL.md
├── agents/openai.yaml
└── references/style.json
```

## 素材与许可

此仓库暂不声明开源许可证，且不包含任何内置参考图片。StyleSpec 仅描述通用的低预算早期 3D CGI 视觉语法，不表示本项目与任何原作品、作者或版权方存在关联。

用户主动提供图片进行转换时，应自行确认拥有相应的使用权利。
