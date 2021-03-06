<style>
  .demo-box.demo-sidebar {
    .el-menu-demo {
      padding-left: 55px;
    }
    .el-menu-vertical-demo {
      width: 210px;
      min-height: 400px;
    }
    .line {
      height: 1px;
      background-color: #e0e6ed;
      margin: 35px -24px;
    }
    h5 {
      font-size: 14px;
      color: #8492a6;
      margin-top: 10px;
    }
    .tac {
      text-align: center;
      
      .el-menu-vertical-demo {
        display: inline-block;
        text-align: left;
      }
    }
  }
</style>


## Sidebar

Sidebar with sub-menus.

::: demo You can use the el-menu-item-group component to create a menu group, and the name of the group is determined by the title prop or a named slot.
```html
<el-row class="tac">
  <el-col :span="8">
    <h5>With icons</h5>
    <el-sidebar default-active="2" class="el-menu-vertical-demo">
      <el-sidebar-item index="1"><i class="el-icon-menu"></i>Navigator One</el-sidebar-item>
      <el-sidebar-item index="2"><i class="el-icon-menu"></i>Navigator Two</el-sidebar-item>
      <el-sidebar-item index="3"><i class="el-icon-setting"></i>Navigator Three</el-sidebar-item>
    </el-sidebar>
  </el-col>
  
  <el-col :span="8">
    <h5>Without icons</h5>
    <el-sidebar default-active="2" class="el-menu-vertical-demo">
      <el-sidebar-submenu index="1">
        <template slot="title">Navigator One</template>
        <el-sidebar-group title="Group One">
          <el-sidebar-item index="1-1">item one</el-sidebar-item>
          <el-sidebar-item index="1-2">item two</el-sidebar-item>
        </el-sidebar-group>
        <el-sidebar-group title="Group Two">
          <el-sidebar-item index="1-3">item three</el-sidebar-item>
        </el-sidebar-group>
        <el-sidebar-submenu index="1-4">
          <template slot="title">item four</template>
          <el-sidebar-item index="1-4-1">item one</el-sidebar-item>
        </el-sidebar-submenu>
      </el-sidebar-submenu>
      <el-sidebar-item index="2">Navigator Two</el-sidebar-item>
      <el-sidebar-item index="3">Navigator Three</el-sidebar-item>
    </el-sidebar>
  </el-col>
  
  <el-col :span="8">
    <h5>Groups</h5>
    <el-sidebar mode="vertical" default-active="1" class="el-menu-vertical-demo">
      <el-sidebar-group title="Group One">
        <el-sidebar-item index="1"><i class="el-icon-message"></i>Navigator One</el-sidebar-item>
        <el-sidebar-item index="2"><i class="el-icon-message"></i>Navigator Two</el-sidebar-item>
      </el-sidebar-group>
      <el-sidebar-group title="Group Two">
        <el-sidebar-item index="3"><i class="el-icon-message"></i>Navigator Three</el-sidebar-item>
        <el-sidebar-item index="4"><i class="el-icon-message"></i>Navigator Four</el-sidebar-item>
      </el-sidebar-group>
    </el-sidebar>
  </el-col>
</el-row>
```
:::



### Menu Attribute
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------- |---------- |-------------  |-------- |
| mode     | menu display mode   | string  |   horizontal/vertical   | vertical |
| theme     | theme color   | string    | light/dark | light |
| default-active | index of currently active menu | string    | — | — |
| default-openeds | array that contains keys of currently active sub-menus  | Array    | — | — |
| unique-opened  |  whether only one sub-menu can be active  | boolean   | — | false   |
| menu-trigger | how sub-menus are triggered, only works when `mode` is 'horizontal' | string    | — | hover |
| router  | whether `vue-router` mode is activated. If true, index will be used as 'path' to activate the route action | boolean   | — | false   |


### Menu Events
| Event Name | Description | Parameters |
|---------- |-------- |---------- |
| select  | callback function when menu is activated | index: index of activated menu, indexPath: index path of activated menu  |
| open  | callback function when sub-menu expands | index: index of expanded sub-menu, indexPath: index path of expanded sub-menu |
| close  | callback function when sub-menu collapses | index: index of collapsed sub-menu, indexPath: index path of collapsed sub-menu |

### SubMenu Attribute
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------- |---------- |-------------  |-------- |
| index     | unique identification   | string  | — | — |

### Menu-Item Attribute
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------- |---------- |-------------  |-------- |
| index     | unique identification   | string  | — | — |
| route     | Vue Router object   | object | — | — |

### Menu-Group Attribute
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------- |---------- |-------------  |-------- |
| title     | group title   | string  | — | — |
