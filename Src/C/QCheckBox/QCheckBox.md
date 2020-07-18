[TOC]



# QCheckBox Class

The QCheckBox widget provides a checkbox with a text label. 

| 属性   | 方法                                                         |
| ------ | ------------------------------------------------------------ |
| 头文件 | #include <QCheckBox>                                         |
| qmake  | QT += widgets                                                |
| 基类   | [QAbstractButton](https://doc.qt.io/qt-5/qabstractbutton.html) |

[List of all members, including inherited members](https://doc.qt.io/qt-5/qcheckbox-members.html)



## Properties

- **[tristate](https://doc.qt.io/qt-5/qcheckbox.html#tristate-prop)** : bool



## Public Functions

|                | **[QCheckBox](https://doc.qt.io/qt-5/qcheckbox.html#QCheckBox-1)**(const QString &*text*, QWidget **parent* = nullptr) |
| -------------- | ------------------------------------------------------------ |
|                | **[QCheckBox](https://doc.qt.io/qt-5/qcheckbox.html#QCheckBox)**(QWidget **parent* = nullptr) |
| virtual        | **[~QCheckBox](https://doc.qt.io/qt-5/qcheckbox.html#dtor.QCheckBox)**() |
| Qt::CheckState | **[checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)**() const |
| bool           | **[isTristate](https://doc.qt.io/qt-5/qcheckbox.html#tristate-prop)**() const |
| void           | **[setCheckState](https://doc.qt.io/qt-5/qcheckbox.html#setCheckState)**(Qt::CheckState *state*) |
| void           | **[setTristate](https://doc.qt.io/qt-5/qcheckbox.html#tristate-prop)**(bool *y* = true) |



## Reimplemented Public Functions

| virtual QSize | **[minimumSizeHint](https://doc.qt.io/qt-5/qcheckbox.html#minimumSizeHint)**() const override |
| ------------- | ------------------------------------------------------------ |
| virtual QSize | **[sizeHint](https://doc.qt.io/qt-5/qcheckbox.html#sizeHint)**() const override |



## Signals

| void | **[stateChanged](https://doc.qt.io/qt-5/qcheckbox.html#stateChanged)**(int *state*) |
| ---- | ------------------------------------------------------------ |
|      |                                                              |



## Protected Functions

| void | **[initStyleOption](https://doc.qt.io/qt-5/qcheckbox.html#initStyleOption)**(QStyleOptionButton **option*) const |
| ---- | ------------------------------------------------------------ |
|      |                                                              |



## Reimplemented Protected Functions

| virtual void | **[checkStateSet](https://doc.qt.io/qt-5/qcheckbox.html#checkStateSet)**() override |
| ------------ | ------------------------------------------------------------ |
| virtual bool | **[event](https://doc.qt.io/qt-5/qcheckbox.html#event)**(QEvent **e*) override |
| virtual bool | **[hitButton](https://doc.qt.io/qt-5/qcheckbox.html#hitButton)**(const QPoint &*pos*) const override |
| virtual void | **[mouseMoveEvent](https://doc.qt.io/qt-5/qcheckbox.html#mouseMoveEvent)**(QMouseEvent **e*) override |
| virtual void | **[nextCheckState](https://doc.qt.io/qt-5/qcheckbox.html#nextCheckState)**() override |
| virtual void | **[paintEvent](https://doc.qt.io/qt-5/qcheckbox.html#paintEvent)**(*QPaintEvent **) override |



## Detailed Description

![img](https://doc.qt.io/qt-5/images/windows-checkbox.png)

A QCheckBox is an option button that can be switched on (checked) or off (unchecked). Checkboxes are typically used to represent features in an application that can be enabled or disabled without affecting others. Different types of behavior can be implemented. For example, a [QButtonGroup](https://doc.qt.io/qt-5/qbuttongroup.html) can be used to group check buttons logically, allowing exclusive checkboxes. However, [QButtonGroup](https://doc.qt.io/qt-5/qbuttongroup.html) does not provide any visual representation.

QCheckBox复选框是一种可以打开（选中）或者关闭（取消选中）的选项按钮。复选框通常在应用程序中用于开启或禁用某项功能而不影响其他功能。可以实现不同类型的行为，例如，可以使用[QButtonGroup](https://doc.qt.io/qt-5/qbuttongroup.html) 对不同的复选框按钮进行逻辑分组，实现复选框间的互斥。但是[QButtonGroup](https://doc.qt.io/qt-5/qbuttongroup.html) 不会提供任何视觉上的显示。

The image below further illustrates the differences between exclusive and non-exclusive checkboxes.

下图进一步说明了互斥复选框和非互斥复选框的区别。

| ![img](https://doc.qt.io/qt-5/images/checkboxes-exclusive.png) | ![img](https://doc.qt.io/qt-5/images/checkboxes-non-exclusive.png) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |

Whenever a checkbox is checked or cleared, it emits the signal [stateChanged](https://doc.qt.io/qt-5/qcheckbox.html#stateChanged)(). Connect to this signal if you want to trigger an action each time the checkbox changes state. You can use [isChecked](https://doc.qt.io/qt-5/qabstractbutton.html#checked-prop)() to query whether or not a checkbox is checked.

复选框每当选中或取消选中时，都会发出信号 [stateChanged](https://doc.qt.io/qt-5/qcheckbox.html#stateChanged)()。如果想在每次复选框变更状态时触发操作，请连接此信号。可以使用[isChecked](https://doc.qt.io/qt-5/qabstractbutton.html#checked-prop)() 来查询复选框当前是否是被选中的。

In addition to the usual checked and unchecked states, QCheckBox optionally provides a third state to indicate "no change". This is useful whenever you need to give the user the option of neither checking nor unchecking a checkbox. If you need this third state, enable it with [setTristate](https://doc.qt.io/qt-5/qcheckbox.html#tristate-prop)(), and use [checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)() to query the current toggle state.

除了通常使用的选中和未选中状态之外，QCheckBox可以选择提供第三种状态来指示“无更改”。当需要为用户提供既不选中也不取消选中的选项时候这将非常有用。可以使用[setTristate](https://doc.qt.io/qt-5/qcheckbox.html#tristate-prop)()来启用第三状态，并可以使用[checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)() 来查询当前的切换状态。



Just like [QPushButton](https://doc.qt.io/qt-5/qpushbutton.html), a checkbox displays text, and optionally a small icon. The icon is set with [setIcon](https://doc.qt.io/qt-5/qabstractbutton.html#icon-prop)(). The text can be set in the constructor or with [setText](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(). A shortcut key can be specified by preceding the preferred character with an ampersand. For example:

类似[QPushButton](https://doc.qt.io/qt-5/qpushbutton.html)，复选框显示文本并可选择地显示一个小图标，通过 [setIcon](https://doc.qt.io/qt-5/qabstractbutton.html#icon-prop)()设置图标。显示的文本可以在构造时设置，或者通过[setText](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)()设置。可以在字母前加上`&`来置顶快捷键，例如：

```
QCheckBox *checkbox = new QCheckBox("C&ase sensitive", this);
```

In this example, the shortcut is *Alt+A*. See the [QShortcut](https://doc.qt.io/qt-5/qshortcut.html#mnemonic) documentation for details. To display an actual ampersand, use '&&'.

在此例子中，快捷键是 *Alt+A*。更多细节请参阅[QShortcut](https://doc.qt.io/qt-5/qshortcut.html#mnemonic) 的文档。若要显示实际的`&`字符，可以使用`&&`。

Important inherited functions: [text](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(), [setText](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(), [text](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(), pixmap(), setPixmap(), accel(), setAccel(), isToggleButton(), [setDown](https://doc.qt.io/qt-5/qabstractbutton.html#down-prop)(), [isDown](https://doc.qt.io/qt-5/qabstractbutton.html#down-prop)(), isOn(), [checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)(), [autoRepeat](https://doc.qt.io/qt-5/qabstractbutton.html#autoRepeat-prop)(), isExclusiveToggle(), [group](https://doc.qt.io/qt-5/qabstractbutton.html#group)(), [setAutoRepeat](https://doc.qt.io/qt-5/qabstractbutton.html#autoRepeat-prop)(), [toggle](https://doc.qt.io/qt-5/qabstractbutton.html#toggle)(), [pressed](https://doc.qt.io/qt-5/qabstractbutton.html#pressed)(), [released](https://doc.qt.io/qt-5/qabstractbutton.html#released)(), [clicked](https://doc.qt.io/qt-5/qabstractbutton.html#clicked)(), [toggled](https://doc.qt.io/qt-5/qabstractbutton.html#toggled)(), [checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)(), and [stateChanged](https://doc.qt.io/qt-5/qcheckbox.html#stateChanged)().

**See also** [QAbstractButton](https://doc.qt.io/qt-5/qabstractbutton.html), [QRadioButton](https://doc.qt.io/qt-5/qradiobutton.html), and [GUI Design Handbook: Check Box](https://doc.qt.io/qt-5/guibooks.html#fowler).



重要的继承函数： [text](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(), [setText](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(), [text](https://doc.qt.io/qt-5/qabstractbutton.html#text-prop)(), pixmap(), setPixmap(), accel(), setAccel(), isToggleButton(), [setDown](https://doc.qt.io/qt-5/qabstractbutton.html#down-prop)(), [isDown](https://doc.qt.io/qt-5/qabstractbutton.html#down-prop)(), isOn(), [checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)(), [autoRepeat](https://doc.qt.io/qt-5/qabstractbutton.html#autoRepeat-prop)(), isExclusiveToggle(), [group](https://doc.qt.io/qt-5/qabstractbutton.html#group)(), [setAutoRepeat](https://doc.qt.io/qt-5/qabstractbutton.html#autoRepeat-prop)(), [toggle](https://doc.qt.io/qt-5/qabstractbutton.html#toggle)(), [pressed](https://doc.qt.io/qt-5/qabstractbutton.html#pressed)(), [released](https://doc.qt.io/qt-5/qabstractbutton.html#released)(), [clicked](https://doc.qt.io/qt-5/qabstractbutton.html#clicked)(), [toggled](https://doc.qt.io/qt-5/qabstractbutton.html#toggled)(), [checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)(), 和 [stateChanged](https://doc.qt.io/qt-5/qcheckbox.html#stateChanged)().

**另请参阅** [QAbstractButton](https://doc.qt.io/qt-5/qabstractbutton.html), [QRadioButton](https://doc.qt.io/qt-5/qradiobutton.html), and [GUI Design Handbook: Check Box](https://doc.qt.io/qt-5/guibooks.html#fowler).



## Property Documentation

### tristate : bool

This property holds whether the checkbox is a tri-state checkbox

The default is false, i.e., the checkbox has only two states.

**Access functions:**

| bool | **isTristate**() const           |
| ---- | -------------------------------- |
| void | **setTristate**(bool *y* = true) |

## Member Function Documentation

### QCheckBox::QCheckBox(const [QString](https://doc.qt.io/qt-5/qstring.html) &*text*, [QWidget](https://doc.qt.io/qt-5/qwidget.html#QWidget) **parent* = nullptr)

Constructs a checkbox with the given *parent* and *text*.

*parent* is passed on to the [QAbstractButton](https://doc.qt.io/qt-5/qabstractbutton.html) constructor.

### QCheckBox::QCheckBox([QWidget](https://doc.qt.io/qt-5/qwidget.html#QWidget) **parent* = nullptr)

Constructs a checkbox with the given *parent*, but with no text.

*parent* is passed on to the [QAbstractButton](https://doc.qt.io/qt-5/qabstractbutton.html) constructor.

### `[signal]`void QCheckBox::stateChanged(int *state*)

This signal is emitted whenever the checkbox's state changes, i.e., whenever the user checks or unchecks it.

*state* contains the checkbox's new [Qt::CheckState](https://doc.qt.io/qt-5/qt.html#CheckState-enum).

### `[virtual]`QCheckBox::~QCheckBox()

Destructor.

### [Qt::CheckState](https://doc.qt.io/qt-5/qt.html#CheckState-enum) QCheckBox::checkState() const

Returns the checkbox's check state. If you do not need tristate support, you can also use [QAbstractButton::isChecked](https://doc.qt.io/qt-5/qabstractbutton.html#checked-prop)(), which returns a boolean.

**See also** [setCheckState](https://doc.qt.io/qt-5/qcheckbox.html#setCheckState)() and [Qt::CheckState](https://doc.qt.io/qt-5/qt.html#CheckState-enum).

### `[override virtual protected]`void QCheckBox::checkStateSet()

Reimplements: [QAbstractButton::checkStateSet](https://doc.qt.io/qt-5/qabstractbutton.html#checkStateSet)().

### `[override virtual protected]`bool QCheckBox::event([QEvent](https://doc.qt.io/qt-5/qevent.html) **e*)

Reimplements: [QAbstractButton::event](https://doc.qt.io/qt-5/qabstractbutton.html#event)(QEvent *e).

### `[override virtual protected]`bool QCheckBox::hitButton(const [QPoint](https://doc.qt.io/qt-5/qpoint.html) &*pos*) const

Reimplements: [QAbstractButton::hitButton](https://doc.qt.io/qt-5/qabstractbutton.html#hitButton)(const QPoint &pos) const.

### `[protected]`void QCheckBox::initStyleOption([QStyleOptionButton](https://doc.qt.io/qt-5/qstyleoptionbutton.html) **option*) const

Initializes *option* with the values from this [QCheckBox](https://doc.qt.io/qt-5/qcheckbox.html). This method is useful for subclasses that require a [QStyleOptionButton](https://doc.qt.io/qt-5/qstyleoptionbutton.html), but do not want to fill in all the information themselves.

**See also** [QStyleOption::initFrom](https://doc.qt.io/qt-5/qstyleoption.html#initFrom)().

### `[override virtual]`[QSize](https://doc.qt.io/qt-5/qsize.html) QCheckBox::minimumSizeHint() const

Reimplements an access function for property: [QWidget::minimumSizeHint](https://doc.qt.io/qt-5/qwidget.html#minimumSizeHint-prop).

### `[override virtual protected]`void QCheckBox::mouseMoveEvent([QMouseEvent](https://doc.qt.io/qt-5/qmouseevent.html) **e*)

Reimplements: [QAbstractButton::mouseMoveEvent](https://doc.qt.io/qt-5/qabstractbutton.html#mouseMoveEvent)(QMouseEvent *e).

### `[override virtual protected]`void QCheckBox::nextCheckState()

Reimplements: [QAbstractButton::nextCheckState](https://doc.qt.io/qt-5/qabstractbutton.html#nextCheckState)().

### `[override virtual protected]`void QCheckBox::paintEvent(*QPaintEvent **)

Reimplements: [QAbstractButton::paintEvent](https://doc.qt.io/qt-5/qabstractbutton.html#paintEvent)(QPaintEvent *e).

### void QCheckBox::setCheckState([Qt::CheckState](https://doc.qt.io/qt-5/qt.html#CheckState-enum) *state*)

Sets the checkbox's check state to *state*. If you do not need tristate support, you can also use [QAbstractButton::setChecked](https://doc.qt.io/qt-5/qabstractbutton.html#checked-prop)(), which takes a boolean.

**See also** [checkState](https://doc.qt.io/qt-5/qcheckbox.html#checkState)() and [Qt::CheckState](https://doc.qt.io/qt-5/qt.html#CheckState-enum).

### `[override virtual]`[QSize](https://doc.qt.io/qt-5/qsize.html) QCheckBox::sizeHint() const

Reimplements an access function for property: [QWidget::sizeHint](https://doc.qt.io/qt-5/qwidget.html#sizeHint-prop).