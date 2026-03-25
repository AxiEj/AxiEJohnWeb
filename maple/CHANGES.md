# Changes vs Upstream (`ClickFF/MAPLE-Website`)

> Branch: `AxiEj/MAPLE-Website @ main`
> Base commit: `b01da53` (Sync upstream)
> Latest commit: `3376dba`

---

## 1. `assets/css/styles.css` — 新增图片样式

新增第 22 节 **Figure / Chart Images**：

- `figure.doc-figure` — 居中、带边框和圆角的图片容器
- `figure.doc-figure img` — 自适应宽高，带 1px 边框与背景色
- `figure.doc-figure figcaption` — 小字灰色图注
- `.figure-row` — 两图并排 flex 布局（max-width 400px/个，`flex-wrap: wrap`）

---

## 2. `tasks/opt/optimization.html` — 更新示例坐标 + 侧边栏

- 示例输入坐标从 3 原子水分子（H₂O）替换为 22 原子有机分子，与各方法页面保持一致
- 侧边栏 Optimization 子项补全 **CG** 和 **SD/CG** 链接

---

## 3. `tasks/opt/opt_lbfgs.html` — 更新 + 新增章节

- 侧边栏新增 **CG**、**SD/CG** 导航链接
- 示例坐标更新为 22 原子分子
- 新增 **Convergence Behaviour** 章节：
  - Fig. 1 — 能量收敛图（`opt/lbfgs/energy_vs_iter_lbfgs.png`）
  - Fig. 2 — 力收敛图（`opt/lbfgs/force_vs_iter_lbfgs.png`）
  - Fig. 3 — 优化轨迹动画 GIF（`opt/lbfgs/inp1_traj.gif`）

---

## 4. `tasks/opt/opt_rfo.html` — 更新 + 新增章节

- 侧边栏新增 **CG**、**SD/CG** 导航链接
- 示例坐标更新为 22 原子分子
- 新增 **Convergence Behaviour** 章节：
  - Fig. 1 — RFO 能量收敛图（`opt/rfo/energy_vs_iter_rfo.png`）
  - Fig. 2 — RFO 力收敛图（`opt/rfo/force_vs_iter_rfo.png`）
  - Fig. 3 — L-BFGS vs RFO 能量对比图（`opt/shared/energy_comparison.png`）

---

## 5. `tasks/opt/opt_sd.html` — 更新 + 新增章节

- 侧边栏新增 **CG**、**SD/CG** 导航链接
- 示例坐标更新为 22 原子分子
- 新增 **Convergence Behaviour** 章节：
  - Fig. 1 — SD 能量收敛图（`opt/sd/energy_vs_iter_sd.png`）
  - Fig. 2 — SD 力收敛图（`opt/sd/force_vs_iter_sd.png`）

---

## 6. `tasks/opt/opt_cg.html` — 全新页面（+296 行）

CG（Conjugate Gradient）优化方法完整文档，包含：

- 方法描述、参数表、示例输入（22 原子分子）
- **Convergence Behaviour** 章节（`opt/cg/` 图片）
- 侧边栏含 L-BFGS / RFO / SD / CG / SD/CG 链接
  （MD 相关链接已移除，待 `feat/pbc-md` 合并后恢复）

---

## 7. `tasks/opt/opt_sdcg.html` — 全新页面（+308 行）

SD/CG（Steepest Descent + Conjugate Gradient）优化方法完整文档，包含：

- 方法描述、参数表、示例输入（22 原子分子）
- **Convergence Behaviour** 章节（`opt/sdcg/` 图片）
- 侧边栏同上（MD 链接已移除）

---

## 8. `index.html` — 移除 MD 新闻条目

- 2025.1 新闻条目移除 "and MD capabilities" 字样（MD 功能尚未发布）

---

## 9. `home1.html` — 全面修复与补全

| 问题 | 修复 |
|---|---|
| 所有链接 `<a href=""></a>文字</a>` 双重闭合标签 | 修正为 `<a href="">文字</a>` |
| Optimization 缺少 SD / CG / SD/CG 入口 | 补全五个方法链接 |
| 方法名不一致（`LBFGS`, `PRFO`, `DIMER`, `STRING`） | 统一为 `L-BFGS`, `P-RFO`, `Dimer`, `String/GSM` |
| 侧边栏 `href="#issues"` / `href="#development"` 为无效锚链接 | 改为 `issues.html` / `development.html` |
| 标题拼写错误 `Solvant` / `Constrain` | 改为 `Solvation` / `Constraints` |
| 版权年份 2025 | 更新为 2026 |

---

## 10. 图片目录（新增 22 个文件）

| 目录 | 内容 |
|---|---|
| `assets/images/opt/lbfgs/` | L-BFGS 能量图、力图、轨迹 GIF |
| `assets/images/opt/rfo/` | RFO 能量图、力图 |
| `assets/images/opt/sd/` | SD 能量图、力图 |
| `assets/images/opt/cg/` | CG 能量图、力图 |
| `assets/images/opt/sdcg/` | SD/CG 能量图、力图 |
| `assets/images/opt/shared/` | L-BFGS vs RFO 对比图及各方法共享图片 |
| `assets/images/opt/tools/` | `plot_opt.py`、`vmd_traj_gif.sh`、`inp1_traj.xyz`、`TOOLS.md`、轨迹 GIF |

---

## 待办

- [ ] `feat/pbc-md` 合并后，在 `opt_cg.html` 和 `opt_sdcg.html` 侧边栏中恢复 MD/CG-MD 链接
