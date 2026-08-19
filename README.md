# NiuLai-image

一个用于生成低成本早期 3D CGI 图像的 Codex Skill：带受控比例误差与不精确装配的 fixed-function 时代实时模型、低 texel 密度的低清 diffuse 贴图、钝化顶点光照、素材包式山林，以及旧式 PC／主机游戏过场与粗糙卡通 VCD 的数字质感。

## 特点

- 使用 MusePool StyleSpec v1 保存结构化风格规则。
- 支持 10 个 Cookbook 基础变量和 4 个 NiuLai 扩展变量。
- 使用 fixed-function 时代中等偏低面数的实时网格：二级形体少、关节和连接生硬，轮廓仍保留足够分段，不退化成方块或大片三角切面。
- 保留身份锚点而不做一比一模型：让头身比、五官间距、肢体尺寸、关节位置、服装贴合和左右对称出现少量且不均匀的可见误差。
- 让粗糙感来自贴在平坦表面上的低清 diffuse 图像：近处可辨的低 texel 色块、远处变脏的 mip 层、UV 拉伸、接缝、镜像和平铺，而不是真实绒毛或立体颗粒。
- 使用近乎无光泽的 diffuse-only／顶点光照：无 AO、反弹光与真实反射，只有 2–4 块宽泛明暗和接触不准的低清阴影。
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
使用 $niulai-low-fi-cgi，生成一张三个萝卜工人在粗糙森林公交站等待末班车的 4:3 粗糙卡通 VCD 动画截图。
```

也可以提供一张待转换图片，并要求保留主体身份、关键服装特征、动作含义、构图和文字，同时迁移 NiuLai 的受控形体误差、低清贴图与早期实时渲染系统。Skill 会锁定原角色，不擅自换成原创替代人物，但默认不会把原图当成一比一 model sheet。

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
