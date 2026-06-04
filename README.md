# Словарь STDL для Visual Studio Code v4.1+

Для версии STDL 4.1+ (Renga 9.1 и выше)

## Возможности

### Файл описания параметров и портов (.json)
- Общая структура;
- Группы параметров;
- Параметры и типы параметров;
- Порты;
- Направления потока;
- Категории систем;
- Параметры арматурных стилей.

### Файл скрипта (.lua)

#### 2D моделирование
- Классы: `CircularProfile`, `RectangularProfile`, `BoundingRect`, `FillArea`, `GeometrySet2D`, `Matrix2D`, `Point2D`;
- Функции создания кривых: `CreateLineSegment2D`, `CreateArc2DByThreePoints`, `CreateCircle2D`, `CreateRectangle2D`, `CreateEllipse2D`, `CreatePolyline2D`, `CreateCompositeCurve2D`, `CreateParametricCurve2D`;
- Операции: `IntersectCurves2D`, `FilletCorners2D`, `ClipCurvesByRegions`.

#### 3D моделирование
- Классы: `Axis3D`, `Matrix3D`, `Placement3D`, `Point3D`, `Vector3D`;
- Функции создания кривых: `CreateLineSegment3D`, `CreateCircle3D`, `CreateArc3DByThreePoints`, `CreateEllipse3D`, `CreateRectangle3D`, `CreatePolyline3D`, `CreateCompositeCurve3D`, `CreateParametricCurve3D`;
- Функции создания тел: `CreateBlock`, `CreateRightCircularCylinder`, `CreateRightEllipticalCylinder`, `CreateRightPrism`, `CreateSphere`, `CreateRightCircularCone`, `CreateRectangularPyramid`, `CreateSweptDiskSolid`;
- Операции: `Extrude`, `Loft`, `Evolve`, `Revolve`, `FilletCorners3D`;
- Булевы операции: `Unite`, `Subtract`, `Intersect`;
- Оси: `CreateXAxis3D`, `CreateYAxis3D`, `CreateZAxis3D`.

#### Параметры операций
- Классы: `EvolutionParameters`, `ExtrusionParameters`, `LoftParameters`, `RevolutionParameters`;
- Атрибуты: `OutwardOffset`, `InwardOffset`, `Direction`, `ForwardDirectionDraftAngle`, `ReverseDirectionDraftAngle`, `GuideCurve`, `ControlPoints`, `ClockwiseRotationAngle`.

#### Пространство имен Style
- Методы: `SetDetailedGeometry`, `SetSymbolicGeometry`, `SetSymbolGeometry`, `SetInsulationSkeleton`, `GetParameterValues`, `GetParameterGroup`, `GetParameter`, `GetPort`.

#### Пространство имен Project
- Методы: `GetRebarStyle`.

#### Класс ReinforcementContainer
- Методы: `AddRebar`, `AddRebarSet`, `AddReinforcementUnit`, `AddReinforcement`.

#### Прочие функции
- `CastToParameterContainer` — приведение сущности к контейнеру параметров.

#### Класс ModelGeometry
- Методы: `AddSolid`, `AddGeometrySet2D`.

#### Класс Port
- Методы: `SetPlacement`, `SetAnchor`, `SetPipeParameters`, `SetDuctParameters`.

#### Классы Parameter и ParameterGroup
- Методы: `GetValue`, `SetVisible`, `SetEnabled`.

#### Армирование (STDL 4.1+)

**Ключевые возможности v4.1:**
- Крюки для U-образных стержней (`LeftHook`, `RightHook`)
- Зоны усиления при раскладке стержней (`ZonedRebarRowParameters`)
- Различные формы выпусков арматурных стержней (`OverhangShapes`)

**Классы и функции:**
- **Классы раскладки**: `RebarRowEdgeProtectionLayout`, `RebarRowUniformLayout`, `EdgeReinforcementLayout`, `EdgeReinforcementCenteredLayout`;
- **Зонированный ряд**: `ZonedRebarRowParameters` (новое в v4.1);
- **Классы сеток**: `DoubleReinforcingMeshParameters`, `ReinforcingMeshParameters`, `ReinforcingMeshSupportsParameters`;
- **Формы деталей**: `CShapedRebarParameters`, `UShapedRebarParameters` (с крюками), `SShapedRebarParameters`;
- **Селекторы**: `VoidingSelector`, `ObjectSideSelector`, `AnyFaceSelector`;
- **Фиксаторы**: `ReinforcingMeshSupportsCellLayout`, `ReinforcingMeshSupportsDistanceLayout`, `RebarChairParameters`;
- **Параметры крюков и свесов**: `RebarHookParameters`, `RebarOverhangParameters` (с формами выпусков);
- **Контейнер**: `ReinforcementContainer`;
- **Вспомогательные**: `Entity`, `BoundingBox`;
- **Атрибуты**: `Layout`, `HorizontalStep`, `VerticalStep`, `Displacements`, `FrontMesh`, `BackMesh`, `Detail`, `EdgeSelectors`, `BendingFactor`, `UseRectangularApproximation`, `Supports`, `RebarStyleId`, `RebarLength`, `LegLength`, `LeftLegLength`, `RightLegLength`, `LeftHook`, `RightHook`, `BendAngle`, `ExtensionLength`, `RotationAngle`, `Overhangs`, `OverhangShapes`, `Hook`, `LongitudinalFreeEnd`, `TransverseFreeEnd`, `StartZones`, `EndZones`, `MainRowParameters`, `MinClearance`;
- **Функции**: `CreateReinforcingMeshInBaseLayer`, `CreateDoubleReinforcingMeshInBaseLayer`, `GetParameterValue`, `GetBoundingBox`, `GetReinforcementUnitStyle`;
- **Шаблоны функций**: `CreateObjectReinforcement`, `SetStyleParameterStates`.

#### Перечисления Style Template API (с выпадающим списком)
- `DuctConnectorType` — типы соединения воздуховодов;
- `PipeConnectorType` — типы соединения трубопроводов;
- `PipeThreadSize` — диаметры резьбового соединения;
- `CoordinateSystem2D` — 2D системы координат (Cartesian, Polar);
- `CoordinateSystem3D` — 3D системы координат (Cartesian, Cylindrical, Spherical);
- `InsulationCapType` — типы завершения изоляции (None, Flat);
- `FlowDirection` — направления потока (Inlet, Outlet, InletAndOutlet);
- `InLayerAlignment` — расположение в слое основы (OuterSide, Center, InnerSide);
- `ModelObjectType` — типы объектов модели;
- `WallSide` — стороны стены;
- `FloorSide` — стороны перекрытия;
- `ReinforcingMeshRowsOrder` — порядок рядов сетки.

#### Функции базовой библиотеки Lua
- `print`, `type`, `tonumber`, `tostring`, `next`, `rawequal`, `rawget`, `rawset`, `select`, `setmetatable`, `require`.

#### Управляющие конструкции Lua
- `if`, `ifel`, `elif`, `for`, `fori`, `forp`, `function`, `local`, `ret`.

#### Математическая библиотека Lua
- `math.abs`, `math.acos`, `math.asin`, `math.atan`, `math.atan2`, `math.ceil`, `math.cos`, `math.cosh`, `math.deg`, `math.exp`, `math.floor`, `math.fmod`, `math.huge`, `math.log`, `math.max`, `math.min`, `math.modf`, `math.pi`, `math.rad`, `math.random`, `math.randomseed`, `math.sin`, `math.sinh`, `math.sqrt`, `math.tan`, `math.tanh`, `math.tointeger`, `math.type`.

#### Библиотека для работы с таблицами Lua
- `table.concat`, `table.insert`, `table.remove`, `table.sort`, `table.pack`, `table.unpack`, `table.move`.

## Изменения в версии v4.1+

### Новые возможности (Renga 9.1+)
- **Крюки для U-образных стержней** — `LeftHook`, `RightHook` с настраиваемыми углами и длиной;
- **Зоны усиления** — `ZonedRebarRowParameters` для переменного шага стержней в пределах ряда;
- **Формы выпусков** — `OverhangShapes` для различных форм выпусков арматурных стержней.

### Новые сниппеты
- `ZonedRebarRowParameters` — зонированный ряд стержней;
- `LeftLegLength`, `RightLegLength` — раздельные ножки для U-образных стержней;
- `LeftHook`, `RightHook` — крюки для U-образных стержней;
- `OverhangShapes` — формы выпусков;
- `StartZones`, `EndZones`, `MainRowParameters`, `MinClearance` — атрибуты зонированного ряда;
- `RebarOverhangParametersWithShapes` — конструктор с формами выпусков;
- `overhangRuleConstant` — правило выпуска с одинаковым значением для всех стержней.

### Исправления
- Устранён дубляж ключа `Length` (переименован в `RebarLength`);
- Обновлены описания атрибутов `Overhangs` (величины выпусков для каждого стержня в ряду).

## Установка

Скопировать файл `STDL_v4.1.code-snippets` в папку:

`%UserProfile%\AppData\Roaming\Code\User\snippets\`

---

## История изменений

### Версия 4.1
- Возможность задания крюков для U-образных стержней (`LeftHook`, `RightHook`);
- Возможность задания зон усиления при раскладке продольных и поперечных стержней (`ZonedRebarRowParameters`);
- Возможность создания различных форм выпусков арматурных стержней (`OverhangShapes`);
- Поддерживается Renga 9.1 и выше.

### Версия 4.0
- Возможность создания шаблона стиля армирования;
- Возможность создания арматурной сетки в слое основы;
- Возможность создания двух арматурных сеток в слое основы с описанием усиления торцов и фиксаторов;
- Возможность добавления арматурного изделия и стержней произвольной формы;
- Поддерживается Renga 9.0 и выше.