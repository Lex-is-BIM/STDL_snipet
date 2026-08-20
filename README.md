# Словарь STDL для Visual Studio Code v4.7+

Для версии STDL 4.7+ (Renga 9.1 и выше)

## Возможности

### Файл описания параметров и портов (.json)

  * Общая структура;
  * Группы параметров;
  * Параметры и типы параметров;
  * Порты;
  * Направления потока;
  * Категории систем;
  * Параметры арматурных стилей.

### Файл скрипта (.lua)

#### 2D моделирование

  * Классы: `CircularProfile`, `RectangularProfile`, `BoundingRect`, `FillArea`, `GeometrySet2D`, `Matrix2D`, `Point2D`;
  * Функции создания кривых: `CreateLineSegment2D`, `CreateArc2DByThreePoints`, `CreateCircle2D`, `CreateRectangle2D`, `CreateEllipse2D`, `CreatePolyline2D`, `CreateCompositeCurve2D`, `CreateParametricCurve2D`;
  * Операции: `IntersectCurves2D`, `FilletCorners2D`, `ClipCurvesByRegions`.

#### 3D моделирование

  * Классы: `Axis3D`, `Matrix3D`, `Placement3D`, `Point3D`, `Vector3D`;
  * Функции создания кривых: `CreateLineSegment3D`, `CreateCircle3D`, `CreateArc3DByThreePoints`, `CreateEllipse3D`, `CreateRectangle3D`, `CreatePolyline3D`, `CreateCompositeCurve3D`, `CreateParametricCurve3D`;
  * Функции создания тел: `CreateBlock`, `CreateRightCircularCylinder`, `CreateRightEllipticalCylinder`, `CreateRightPrism`, `CreateSphere`, `CreateRightCircularCone`, `CreateRectangularPyramid`, `CreateSweptDiskSolid`;
  * Операции: `Extrude`, `Loft`, `Evolve`, `Revolve`, `FilletCorners3D`;
  * Булевы операции: `Unite`, `Subtract`, `Intersect`;
  * Оси: `CreateXAxis3D`, `CreateYAxis3D`, `CreateZAxis3D`.

#### Параметры операций

  * Классы: `EvolutionParameters`, `ExtrusionParameters`, `LoftParameters`, `RevolutionParameters`;
  * Атрибуты: `OutwardOffset`, `InwardOffset`, `Direction`, `ForwardDirectionDraftAngle`, `ReverseDirectionDraftAngle`, `GuideCurve`, `ControlPoints`, `ClockwiseRotationAngle`.

#### Пространство имен Style

  * Методы: `SetDetailedGeometry`, `SetSymbolicGeometry`, `SetSymbolGeometry`, `SetInsulationSkeleton`, `GetParameterValues`, `GetParameterGroup`, `GetParameter`, `GetPort`.

#### Класс ReinforcementContainer (v4.7)

  * Методы: `AddRebar`, `AddRebarSet` (с `ReinforcementRole`), `AddReinforcementUnit`, `AddReinforcement`.

#### Прочие функции и классы (v4.7)

  * `CastToParameterContainer` — приведение сущности к контейнеру параметров.
  * `GetRebarStyle` — глобальная функция получения стиля стержня по ID.
  * `GetParameterValue`, `GetBoundingBox`, `GetReinforcementUnitStyle`.

#### Класс ModelGeometry

  * Методы: `AddSolid`, `AddGeometrySet2D`.

#### Класс Port

  * Методы: `SetPlacement`, `SetAnchor`, `SetPipeParameters`, `SetDuctParameters`.

#### Классы Parameter и ParameterGroup

  * Методы: `GetValue`, `SetVisible`, `SetEnabled`.

#### Армирование (STDL 4.7+)

**Новое в v4.7:**
  * Поддержка `ReinforcementRole` (Structural / Auxiliary) для стержней и деталей;
  * Арматурные изделия: `ReinforcementUnitRowParameters`, `ReinforcementUnitRowInSectionParameters`, `ZonedReinforcementUnitRowParameters`;
  * Новые раскладки: `ReinforcementUnitEdgeProtectionLayout`, `ReinforcementUnitUniformLayout`, `EdgeReinforcementRebarSyncLayout`;
  * Исправлена сигнатура `RebarChairParameters` (baseLength, legLength, height);
  * Добавлены методы `AddRebar` и `AddRebarSet` с параметром `oReinforcementRole`;
  * Добавлена функция `CreateReinforcementUnitsInBaseLayer`.

**Классы и функции:**
  * **Классы раскладки:** `RebarRowEdgeProtectionLayout`, `RebarRowUniformLayout`, `EdgeReinforcementCenteredLayout`, `EdgeReinforcementRebarSyncLayout`;
  * **Зонированный ряд:** `ZonedRebarRowParameters`;
  * **Классы сеток:** `DoubleReinforcingMeshParameters`, `ReinforcingMeshParameters`, `ReinforcingMeshSupportsParameters`;
  * **Формы деталей:** `CShapedRebarParameters`, `UShapedRebarParameters` (с крюками), `SShapedRebarParameters`, `RebarChairParameters`;
  * **Селекторы:** `VoidingSelector`, `ObjectSideSelector`, `AnyFaceSelector`;
  * **Фиксаторы:** `ReinforcingMeshSupportsCellLayout`, `ReinforcingMeshSupportsDistanceLayout`;
  * **Параметры:** `RebarHookParameters`, `RebarOverhangParameters`, `RebarBendingSegment`, `RebarOverhangShape`;
  * **Контейнер:** `ReinforcementContainer`;
  * **Арматурные изделия:** `ReinforcementUnitRowParameters`, `ReinforcementUnitRowInSectionParameters`, `ZonedReinforcementUnitRowParameters`;
  * **Перечисления:** `ReinforcementRole` (Structural, Auxiliary);
  * **Функции:** `CreateReinforcingMeshInBaseLayer`, `CreateDoubleReinforcingMeshInBaseLayer`, `CreateReinforcementUnitsInBaseLayer`.

#### Перечисления Style Template API (с выпадающим списком)

  * `DuctConnectorType` — типы соединения воздуховодов;
  * `PipeConnectorType` — типы соединения трубопроводов;
  * `PipeThreadSize` — диаметры резьбового соединения;
  * `CoordinateSystem2D` — 2D системы координат (Cartesian, Polar);
  * `CoordinateSystem3D` — 3D системы координат (Cartesian, Cylindrical, Spherical);
  * `InsulationCapType` — типы завершения изоляции (None, Flat);
  * `FlowDirection` — направления потока (Inlet, Outlet, InletAndOutlet);
  * `InLayerAlignment` — расположение в слое основы (OuterSide, Center, InnerSide);
  * `ModelObjectType` — типы объектов модели;
  * `WallSide` — стороны стены;
  * `FloorSide` — стороны перекрытия;
  * `ReinforcingMeshRowsOrder` — порядок рядов сетки;
  * `ReinforcementRole` — роль армирования (Structural, Auxiliary).

#### Функции базовой библиотеки Lua, управляющие конструкции, математическая библиотека, библиотека для работы с таблицами

  * Полный набор сниппетов для всех стандартных функций и конструкций Lua.

## Изменения в версии v4.7

### Новые возможности (Renga 9.1+)

  * **Роль армирования** — `ReinforcementRole` (Structural / Auxiliary) для стержней, деталей и рядов;
  * **Арматурные изделия** — поддержка `ReinforcementUnitRowParameters`, `ReinforcementUnitRowInSectionParameters`, `ZonedReinforcementUnitRowParameters`;
  * **Новые раскладки** — `ReinforcementUnitEdgeProtectionLayout`, `ReinforcementUnitUniformLayout`, `EdgeReinforcementRebarSyncLayout`;
  * **Обновленные методы** — `AddRebar` и `AddRebarSet` теперь принимают `ReinforcementRole`;
  * **Новая функция** — `CreateReinforcementUnitsInBaseLayer` для создания арматурных изделий в слое основы.

### Исправления

  * Исправлена сигнатура `RebarChairParameters` на `(rebarStyleId, baseLength, legLength, height)`;
  * Исправлена сигнатура `CreateDoubleReinforcingMeshInBaseLayer` (добавлены `oFrontOffset`, `oBackOffset`);
  * `GetRebarStyle` исправлен как глобальная функция;
  * Добавлены недостающие классы: `Parameter`, `ParameterContainer`, `ParameterGroup`, `FoundationShape`.

## Установка

Скопировать файлы `STDL_v4.7.code-snippets` и `STDL_v4.7-json.code-snippets` в папку:

`%UserProfile%\AppData\Roaming\Code\User\snippets\`

## История изменений

### Версия 4.7

  * Добавлена поддержка `ReinforcementRole` (Structural / Auxiliary);
  * Добавлены классы для арматурных изделий (v4.2 API);
  * Добавлены новые раскладки для арматурных изделий;
  * Исправлены сигнатуры ключевых методов и конструкторов;
  * Добавлены недостающие классы `Parameter`, `ParameterContainer`, `ParameterGroup`, `FoundationShape`;
  * `GetRebarStyle` исправлен как глобальная функция.

### Версия 4.1

  * Возможность задания крюков для U-образных стержней (`LeftHook`, `RightHook`);
  * Возможность задания зон усиления (`ZonedRebarRowParameters`);
  * Возможность создания различных форм выпусков (`OverhangShapes`).

### Версия 4.0

  * Возможность создания шаблона стиля армирования;
  * Возможность создания арматурной сетки в слое основы;
  * Возможность создания двух арматурных сеток в слое основы с описанием усиления торцов и фиксаторов.