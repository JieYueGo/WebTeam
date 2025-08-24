# 设计规范 - 登录注册页面

## 1. 设计原则
- **简洁高效**：简化用户注册和登录流程，减少认知负担
- **安全可靠**：通过视觉设计传达安全感，保护用户信息
- **一致性**：保持与产品整体设计风格统一
- **无障碍**：确保所有用户，包括有特殊需求的用户都能便捷使用
- **响应式**：提供一致的体验 across all device sizes

## 2. 色彩系统
### 2.1 主色彩
- **主色**：#3B82F6 (蓝色) - 传达信任和专业感
  - 使用场景：按钮、标题、强调元素
- **辅助色**：#10B981 (绿色) - 表示成功状态
  - 使用场景：成功提示、验证通过
- **强调色**：#EF4444 (红色) - 表示错误状态
  - 使用场景：错误提示、警告信息

### 2.2 中性色
- **文字色**：#1F2937 (深灰) - 主要文字
  - #4B5563 (中灰) - 次要文字
  - #6B7280 (浅灰) - 辅助文字
- **背景色**：#FFFFFF (白色) - 页面背景
  - #F9FAFB (浅灰) - 卡片背景
  - #F3F4F6 (中灰) - 输入框背景
- **边框色**：#E5E7EB (浅灰) - 常规边框
  - #D1D5DB (中灰) - 聚焦边框

### 2.3 功能色
- **成功**：#10B981 (绿色)
- **警告**：#F59E0B (黄色)
- **错误**：#EF4444 (红色)
- **信息**：#3B82F6 (蓝色)

## 3. 字体系统
### 3.1 字体家族
- **中文字体**：PingFang SC, Microsoft YaHei, sans-serif
- **英文字体**：Inter, Roboto, sans-serif
- **等宽字体**：Consolas, Menlo, monospace

### 3.2 字体层级
- **大标题**：24px, 字重700, 行高1.2
- **中标题**：20px, 字重600, 行高1.3
- **小标题**：16px, 字重600, 行高1.4
- **正文**：14px, 字重400, 行高1.5
- **辅助文字**：12px, 字重400, 行高1.4

## 4. 间距系统
### 4.1 间距尺度
- **基础单位**：4px
- **常用间距**：8px, 16px, 24px, 32px, 48px
- **使用规则**：
  - 小间距(8px)：按钮内边距、图标间距
  - 中间距(16px)：元素间距、表单字段间距
  - 大间距(24px/32px)：模块间距、页面边距

### 4.2 布局间距
- **页面边距**：
  - 桌面端：左右各32px
  - 平板端：左右各24px
  - 移动端：左右各16px
- **模块间距**：24px
- **元素间距**：16px
- **响应式调整**：间距随屏幕尺寸减小而适当缩减

## 5. 图标系统
### 5.1 图标风格
- **风格**：线性图标，24px×24px网格
- **线条粗细**：2px
- **圆角**：4px

### 5.2 图标使用
- **命名规范**：使用kebab-case命名法，如 `user-icon`, `lock-icon`
- **使用场景**：
  - 用户图标：用户名输入框
  - 锁图标：密码输入框
  - 邮箱图标：邮箱输入框
  - 箭头图标：按钮、导航
  - 提示图标：错误/成功提示

## 6. 组件库
### 6.1 基础组件
#### 按钮
```
.primary-button {
  background-color: #3B82F6;
  color: white;
  padding: 10px 16px;
  border-radius: 6px;
  font-weight: 600;
  transition: background-color 0.2s;
}

.primary-button:hover {
  background-color: #2563EB;
}

.primary-button:active {
  background-color: #1D4ED8;
}

.primary-button:disabled {
  background-color: #93C5FD;
  cursor: not-allowed;
}
```

#### 输入框
```
.input-field {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid #E5E7EB;
  border-radius: 6px;
  background-color: #F9FAFB;
  transition: border-color 0.2s;
}

.input-field:focus {
  outline: none;
  border-color: #3B82F6;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
}

.input-field.error {
  border-color: #EF4444;
}

.input-field.success {
  border-color: #10B981;
}
```

#### 标签
```
.label {
  display: block;
  margin-bottom: 6px;
  font-weight: 500;
  color: #1F2937;
}
```

#### 提示信息
```
.error-message {
  color: #EF4444;
  font-size: 12px;
  margin-top: 4px;
}

.success-message {
  color: #10B981;
  font-size: 12px;
  margin-top: 4px;
}
```

### 6.2 复合组件
#### 表单组
```
.form-group {
  margin-bottom: 16px;
}
```

#### 卡片
```
.card {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  padding: 24px;
}
```

#### 模态框
```
.modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-content {
  background-color: white;
  border-radius: 8px;
  padding: 24px;
  width: 90%;
  max-width: 400px;
}
```

## 7. 页面模板
### 7.1 页面布局
#### 登录/注册页面布局
```
.page-container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #F9FAFB;
  padding: 24px;
}

.auth-card {
  width: 100%;
  max-width: 400px;
}

.form-header {
  margin-bottom: 24px;
  text-align: center;
}

.form-footer {
  margin-top: 16px;
  text-align: center;
}
```

### 7.2 页面示例
#### 登录页面
- 标题：登录
- 表单字段：
  - 用户名/邮箱
  - 密码
  - 记住我（复选框）
- 按钮：登录
- 辅助链接：忘记密码？
- 底部文字：还没有账号？立即注册

#### 注册页面
- 标题：注册
- 表单字段：
  - 用户名
  - 邮箱
  - 密码
  - 确认密码
- 按钮：注册
- 底部文字：已有账号？立即登录

#### 忘记密码页面
- 标题：重置密码
- 表单字段：
  - 邮箱
  - 验证码
  - 新密码
  - 确认新密码
- 按钮：发送验证码、重置密码
- 底部文字：返回登录

## 8. 交互规范
### 8.1 交互模式
- **表单验证**：实时验证，字段失去焦点时显示错误提示
- **按钮状态**：
  - 正常状态：主色
  - 悬停状态：主色加深
  - 点击状态：主色更深
  - 禁用状态：灰色，不可点击
- **加载状态**：按钮文本替换为加载动画
- **表单提交**：
  - 提交时禁用按钮，显示加载状态
  - 成功/失败后恢复按钮状态，显示相应提示

### 8.2 动效设计
- **按钮点击**：轻微缩放效果 (0.98倍)
- **表单提交**：加载动画旋转效果
- **页面切换**：淡入淡出过渡
- **错误/成功提示**：轻微抖动效果引起注意

### 8.3 无障碍设计
- **键盘导航**：支持Tab键切换焦点，Enter键提交表单
- **屏幕阅读器**：所有表单元素添加适当的aria标签
- **色彩对比度**：文本与背景对比度至少达到4.5:1
- **焦点样式**：清晰的焦点环，不依赖颜色传递信息

---
**文档版本**：V1.0
**创建日期**：2025-08-24
**更新日期**：2025-08-24
**创建人**：设计师Agent