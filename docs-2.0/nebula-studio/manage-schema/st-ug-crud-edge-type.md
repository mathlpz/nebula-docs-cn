# 操作 Edge type

在 Nebula Graph 数据库中创建图空间后，用户可能需要创建 Edge type（边类型）。用户可以选择使用 **控制台** 或者 **Schema** 操作 Edge type。本文仅说明如何使用 **Schema** 操作 Edge type。

## 支持版本

Studio v{{ studio.release }} 及以后版本。请更新版本，详细操作参考[版本更新](../about-studio/st-ug-release-note.md)。

## 前提条件

在 Studio 上操作 Edge type 之前，用户必须确认以下信息：

- Studio 已经连接到 Nebula Graph 数据库。

- 图空间已经创建。

- 当前登录的账号拥有 GOD、ADMIN 或者 DBA 的权限。

## 创建边类型

按以下步骤使用 **Schema** 创建 Edge type：

1. 在顶部导航栏中，点击 **Schema** 页签。

2. 在 **图空间列表** 中，找到图空间，点击图空间名称或者在 **操作** 列中点击 **Schema**。

3. 在 **当前图空间** 里确认图空间名称。用户也可以通过选择图空间名称切换图空间。

4. 点击 **边类型** 页签，并点击 **+ 创建** 按钮。

5. 在 **创建** 页面上，完成以下设置：

  1. **名称**：按提示信息输入合规的 Edge type 名称。本示例中，输入 `serve`。
  
  2. （可选）如果 Edge type 需要描述，可以在 **描述** 输入相应内容。
  
  3. （可选）如果 Edge type 需要属性，点击勾选框 **定义属性** 并点击 **+ 添加属性**，完成以下操作：

    - 输入属性名称、数据类型和默认值。
    - 如果一个 Edge type 有多个属性，可以点击 **添加属性** 按钮，并定义属性。
    - 如果要删除某个属性，在该属性所在行，点击 **删除**。

  4. （可选）Tag 未设置索引时，用户可以设置 TTL：在 **设置 TTL（存活时间）** 模块左上角，点击勾选框，在列表中设置 `TTL_COL` 和 `TTL_DURATION` 参数信息。关于这两个参数的详细信息，参考 [TTL 配置](../../3.ngql-guide/8.clauses-and-options/ttl-options.md "点击前往 Nebula Graph 网站")。

6. 完成设置后，在 **对应的 nGQL 语句** 面板上，用户能看到与上述配置等价的 nGQL 语句。  
![定义 Edge type action 的属性](https://docs-cdn.nebula-graph.com.cn/figures/st-ug-022.png "定义 Edge type")

7. 确认无误后，点击 **创建** 按钮。

   如果 Edge Type 创建成功，**标签** 面板会显示这个 Tag 的属性列表。

## 修改 Edge type

按以下步骤使用 **Schema** 修改 Edge type：

1. 在顶部导航栏中，点击 **Schema** 页签。

2. 在 **图空间列表** 中，找到图空间，点击图空间名称或者在 **操作** 列中点击 **Schema**。

3. 在 **当前图空间** 里确认图空间名称。用户也可以通过选择图空间名称完成图空间切换。

4. 点击 **边类型** 页签，找到需要修改的 Edge Type，并在 **操作** 列中，点击 ![表示修改的图标](https://docs-cdn.nebula-graph.com.cn/figures/Setup.png "修改") 图标。

5. 在 **编辑** 页面，用户可以选择以下操作：

   - 如果要修改描述：在 **描述** 下方，点击编辑进行修改，点击 **确认** 后完成修改。
   - 如果要修改属性：在 **定义属性** 面板上，找到需要修改的属性，在右侧点击 **编辑**，再修改属性的数据类型和默认值。之后，点击 **确认** 或者 **取消** 完成修改。
   - 如果要删除属性：在 **定义属性** 面板上，找到需要删除的属性，在右侧点击 **删除**，经确认后，删除属性。
   - 如果要添加属性：在 **定义属性**面板上，点击 **+ 添加属性** 按钮，添加属性信息。详细操作，参考 创建 Tag 面板。
   - 如果配置了 TTL，要修改 TTL 信息：在 **设置 TTL** 面板上，修改 `TTL_COL` 和 `TTL_DURATION` 配置。
   - 如果要删除已经配置的 TTL 信息：在 **设置 TTL** 面板的左上角，点击勾选框，取消选择。
   - 如果要配置 TTL 信息：在 **使用 TTL** 面板的右上角，点击勾选框，开始设置 TTL 信息。

    !!! note

        TTL 与索引的共存问题，详情请见 [TTL](../../3.ngql-guide/8.clauses-and-options/ttl-options.md)。

6. 完成设置后，在 **对应的 nGQL 语句** 面板上，用户能看到修改后的 nGQL 语句。

## 删除 Edge type

!!! danger
    删除 Edge type 前先确认[影响](../../3.ngql-guide/11.edge-type-statements/2.drop-edge.md)，已删除的数据如未[备份](../../backup-and-restore/3.manage-snapshot.md)无法恢复。

按以下步骤使用 **Schema** 删除 Edge type：

1. 在顶部导航栏中，点击 **Schema** 页签。

2. 在 **图空间列表** 中，找到图空间，点击图空间名称或者在 **操作** 列中点击 **Schema**。

3. 在 **当前图空间** 里确认图空间名称。用户也可以通过选择图空间名称切换图空间。

4. 点击 **边类型** 页签，找到需要修改的 Edge type，并在 **操作** 列中，点击 ![表示删除的图标](https://docs-cdn.nebula-graph.com.cn/figures/alert-delete.png) 图标。

5. 在弹出的对话框中点击 **确认**。

## 后续操作

Edge type 创建成功后，用户可以在 **控制台** 上逐条插入边数据，或者使用 **导入** 功能批量插入边数据。
