# Словарь STDL для Visual Studio Code v3.0

Для версии STDL 3.0

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

#### Перечисления Style Template API (с выпадающим списком)
- `DuctConnectorType` — типы соединения воздуховодов;
- `PipeConnectorType` — типы соединения трубопроводов;
- `PipeThreadSize` — диаметры резьбового соединения;
- `CoordinateSystem2D` — 2D системы координат (Cartesian, Polar);
- `CoordinateSystem3D` — 3D системы координат (Cartesian, Cylindrical, Spherical);
- `InsulationCapType` — типы завершения изоляции (None, Flat);
- `FlowDirection` — направления потока (Inlet, Outlet, InletAndOutlet).

#### Функции базовой библиотеки Lua
- `print`, `type`, `tonumber`, `tostring`, `next`, `rawequal`, `rawget`, `rawset`, `select`, `setmetatable`, `require`.

#### Управляющие конструкции Lua
- `if`, `ifel`, `elif`, `for`, `fori`, `forp`, `function`, `local`, `ret`.

#### Математическая библиотека Lua
- `math.abs`, `math.acos`, `math.asin`, `math.atan`, `math.atan2`, `math.ceil`, `math.cos`, `math.cosh`, `math.deg`, `math.exp`, `math.floor`, `math.fmod`, `math.log`, `math.max`, `math.min`, `math.modf`, `math.pi`, `math.rad`, `math.random`, `math.randomseed`, `math.sin`, `math.sinh`, `math.sqrt`, `math.tan`, `math.tanh`, `math.tointeger`, `math.type`.

#### Библиотека для работы с таблицами Lua
- `table.concat`, `table.insert`, `table.remove`, `table.sort`, `table.pack`, `table.unpack`, `table.move`.

## Изменения в версии v3.0

- Добавлены перечисления `CoordinateSystem2D`, `CoordinateSystem3D`, `InsulationCapType`, `FlowDirection` с выпадающим списком;
- Добавлен метод `Style.SetInsulationSkeleton` для задания остова изоляции;
- Добавлен метод `CastToParameterContainer`;
- Исправлены префиксы методов `GetValue` (с `.` на `:`), `Trim3D` (с `:Trim()` на `:Trim3D()`);
- Исправлены отсутствующие скобки у `FillArea`, `AddRebar`, `AddRebarSet`, `CastToParameterContainer`;
- Удалены дублирующиеся сниппеты (`fun`, `req`, старый `CoordinateSystem2D`);
- Все enum объединены в единый формат с выбором значения через Tab.

## Установка
Скопировать файл `STDL_v3.code-snippets` в папку:
`%UserProfile%\AppData\Roaming\Code\User\snippets\`