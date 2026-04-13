# Словарь STDL для Visual Studio Code v4.0 (Preview)

Для версии STDL 4.0

## Возможности

### Файл описания параметров и портов (.json)
- Общая структура;
- Группы параметров;
- Параметры и типы параметров;
- Порты;
- Направления потока;
- Категории систем.

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
- Методы: `SetDetailedGeometry`, `SetSymbolicGeometry`, `SetSymbolGeometry`, `SetInsulationSkeleton`, `GetParameterValues`, `GetParameterGroup`, `GetParameter`, `GetPort`, `AddRebar`, `AddRebarSet`.

#### Пространство имен Project
- Методы: `GetRebarStyle`.

#### Прочие функции
- `CastToParameterContainer` — приведение сущности к контейнеру параметров.

#### Класс ModelGeometry
- Методы: `AddSolid`, `AddGeometrySet2D`.

#### Класс Port
- Методы: `SetPlacement`, `SetAnchor`, `SetPipeParameters`, `SetDuctParameters`.

#### Классы Parameter и ParameterGroup
- Методы: `GetValue`, `SetVisible`, `SetEnabled`.

#### NEW! Армирование (STDL 4.0)
- Классы: `DoubleReinforcingMeshParameters`, `EdgeReinforcementParameters`, `RebarRowParameters`, `ReinforcingMeshParameters`, `ReinforcementContainer`, `CShapedRebarParameters`, `UShapedRebarParameters`, `VoidingSelector`, `ObjectSideSelector`, `RebarOverhangRule`, `ChairRebarParameters`, `ReinforcingMeshSupportsCellLayout`, `ReinforcingMeshSupportsDistanceLayout`, `BoundingBox`, `Entity`;
- Атрибуты: `MinClearance`, `Strategy`, `Displacement`, `OverhangRules`, `BendingFactor`, `UseRectangularApproximation`, `Supports`, `RebarStyleId`, `Length`, `BaseLength`, `LegLength`;
- Функции: `CreateReinforcingMeshInBaseLayer`, `CreateDoubleReinforcingMeshInBaseLayer`, `GetParameterValue`, `GetBoundingBox`, `GetReinforcementUnitStyle`.

#### Перечисления Style Template API (с выпадающим списком)
- `DuctConnectorType` — типы соединения воздуховодов;
- `PipeConnectorType` — типы соединения трубопроводов;
- `PipeThreadSize` — диаметры резьбового соединения;
- `CoordinateSystem2D` — 2D системы координат (Cartesian, Polar);
- `CoordinateSystem3D` — 3D системы координат (Cartesian, Cylindrical, Spherical);
- `InsulationCapType` — типы завершения изоляции (None, Flat);
- `FlowDirection` — направления потока (Inlet, Outlet, InletAndOutlet);
- NEW! `InLayerAlignment` — расположение в слое основы (Left, Center, Right);
- NEW! `ModelObjectType` — типы объектов модели (Wall, Floor, Door, Window, Roof, Beam, Column, Hole, Opening, IsolatedFoundation, WallFoundation, Ramp, Stair);
- NEW! `WallSide` — стороны стены (Left, Right, Top, Bottom, Front, Back);
- NEW! `FloorSide` — стороны перекрытия (Top, Bottom, Side);
- NEW! `RebarLinearLayoutStrategy` — стратегия раскладки стержней (WithSupportRebars, Uniform);
- NEW! `ReinforcingMeshRowsOrder` — порядок рядов сетки (LongitudinalInFront, TransverseInFront).

#### Функции базовой библиотеки Lua
- `print`, `type`, `tonumber`, `tostring`, `next`, `rawequal`, `rawget`, `rawset`, `select`, `setmetatable`, `require`.

#### Управляющие конструкции Lua
- `if`, `ifel`, `elif`, `for`, `fori`, `forp`, `function`, `local`, `ret`.

#### Математическая библиотека Lua
- `math.abs`, `math.acos`, `math.asin`, `math.atan`, `math.atan2`, `math.ceil`, `math.cos`, `math.cosh`, `math.deg`, `math.exp`, `math.floor`, `math.fmod`, `math.log`, `math.max`, `math.min`, `math.modf`, `math.pi`, `math.rad`, `math.random`, `math.randomseed`, `math.sin`, `math.sinh`, `math.sqrt`, `math.tan`, `math.tanh`, `math.tointeger`, `math.type`.

#### Библиотека для работы с таблицами Lua
- `table.concat`, `table.insert`, `table.remove`, `table.sort`, `table.pack`, `table.unpack`, `table.move`.

## Изменения в версии v4.0 (Preview)

### Добавлено
- **Армирование**: полный набор классов, атрибутов и функций для создания арматурных сеток;
- **Селекторы граней**: `VoidingSelector`, `ObjectSideSelector`;
- **Формы деталей**: `CShapedRebarParameters`, `UShapedRebarParameters`;
- **Фиксаторы сетки**: `ReinforcingMeshSupportsCellLayout`, `ReinforcingMeshSupportsDistanceLayout`, `ChairRebarParameters`;
- **Новые перечисления**: `InLayerAlignment`, `ModelObjectType`, `WallSide`, `FloorSide`, `RebarLinearLayoutStrategy`, `ReinforcingMeshRowsOrder`;
- **Новые функции**: `GetParameterValue`, `GetBoundingBox`, `GetReinforcementUnitStyle`;
- **Новые классы**: `Entity`, `BoundingBox`.

### Исправлено
- Префикс `GetValue` изменён с `.` на `:`;
- Префикс `Trim3D` изменён с `:Trim()` на `:Trim3D()`;
- Добавлены отсутствующие скобки у `FillArea`, `AddRebar`, `AddRebarSet`, `CastToParameterContainer`;
- Удалены дублирующиеся сниппеты.

## Установка

Скопировать файл `STDL_v4.code-snippets` в папку:

`%UserProfile%\AppData\Roaming\Code\User\snippets\`

## Совместимость

- STDL версии 4.0 и выше;
- Renga версии 4.0 и выше (для функций армирования).

## Статус

**Preview** — предварительная версия. Функции армирования проходят тестирование.