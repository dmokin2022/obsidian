### Classes

``` c++
Class Foo {
public:
	Foo(int32_t _age, std::string _name);
	~Foo();
	Foo(const Foo &&);

public:
	void Init();
	void Deinit();

public:
	//  Если структура необходима
	struct SomeStruct; // Forward decalaration

public:
	void Start(SomeStruct _s);
	void Stop();

public:
	GetName() const;
	SetName(_name);

	GetAge() const;
	SetAge(_age);

public:
	struct SomeStruct {
		...
	};

protected:
	void someProtectedMethod(); 

protected:
	int32_t some_value;

private:
	void somePrivateMethod();

private:
	int32_t age;
	std::string name;
};
```
Конструкторы и деструкторы выносить в cpp, даже если дефолтный.
Если у конструктора один параметр, то делаем конструктор explicit. 


### Functions 

Параметры начинаются с _
Используем snake case.
``` c++
Rect SomeFunc(int32_t _x, int32_t _y, int32_t _width, int32_t _height) {
	Rect some_rect;
	some_rect.x = _x;
	some_rect.y = _y;
	some_rect.width = _width;
	some_rect.height = _height;
	return some_rect;
}
```

### Structures

``` c++
struct Bar {
	std::string name;
	uint32_t age;
};
```

### Enums

``` c++
enum class ROLE : uint8_t {
	USER,
	OPERATOR,
	ADMIN,

	COUNT
};
```

Константы, если примитивный тип в единственном числе, то называем с k_.

``` c++
	const int k_var_test;
	const int k_var_test2;
```

Если во множественном числе, то без k_:

``` c++
	const int var_test[10];
	const int var_test2[10];
```

Остальные константы тоже без k_:

``` c++
const std::map<int, std::string> channels; 
```

### Создание псевдонимов.

``` c++
struct Sample {
	...
};

// Необходимо оставлять Map в названии типа.
using SampleMap = <std::string, Sample>;

// С вектором можно не делать упоминание о типе.
using Buffer = std::vector<uint8_t>
```

Делаем упоминание о типе в тех случаях, когда контейнер имеет довольно специфичный функционал: 

``` c++
using SomeQueue = std::queue<std::vector<std::string>>;
```