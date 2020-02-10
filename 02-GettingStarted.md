# 入门

## Codeception 语法

Codeception 遵循简易命名规范，以便利于记忆与理解其方法名称。

- **Actions** 动作以简单的英语动词开头，例如 `click` 或 `fill`。例如：

```php
    $I->click('Login');
    $I->fillField('#input-username', 'John Dough');
    $I->pressKey('#input-remarks', 'foo');
```

- **Assertions** 断言始终以 `see` 或 `dontSee` 开头。例如：

```php
    $I->see('Welcome');
    $I->seeInTitle('My Company');
    $I->seeElement('nav');
    $I->dontSeeElement('#error-message');
    $I->dontSeeInPageSource('<section class="foo">');\
```
- **Grabbers** 用于获取数据。其返回值应另存为变量，以便稍后使用。例如：

```php
    $method = $I->grabAttributeFrom('#login-form', 'method');
    $I->assertEquals('post', $method);
```

## Actors

`Actor` 是 Codeception 主要概念之一，即模拟实际行为，共三个 `Actor`：

- `UnitTester` 单元测试
- `FunctionalTester` 功能测试
- `AcceptanceTester` 验收测试

`Actor` 类的方法通常继承自 Codeception 模块。

```php
php vendor/bin/codecept build
```

## 编写测试示例

Codeception 测试格式为 `Cest` (Codecept + Test)。要开始编写测试，须先创建一个新的 Cest 文件，我们可能通过以下命令来创建：

```php
php vendor/bin/codecept generate:cest acceptance Signin
```
