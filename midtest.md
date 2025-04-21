# 1번
```cpp
#include<iostream>
#include<string>
using namespace std;
class Person {
	int age;
	std::string name;
public:
	Person(int a, std::string b) : age(a), name(b) {}
	void displayInfo() {
		std::cout << age << name << std::endl;
	}
};
int main() {
	Person p(25, "함성모");
	p.displayInfo();
}
```
# 2번
```cpp
#include<iostream>
int Add(int a, int b) {
	return a + b;
}
double Add(double a, double b) {
	return a + b;
}
int main() {
	std::cout << Add(12, 34) << std::endl;
	std::cout << Add(11.11, 22.22) << std::endl;
}
```
# 3번
```cpp
#include<iostream>
using namespace std;
class Shape {
public:
	virtual double area() = 0;
};
class Circle : public Shape {
private:
	double radius;
public:
	Circle(double a) : radius(a) {}
	double area() override {
		return 3.14 * radius * radius;
	}
};
class Rectangle : public Shape {
private:
	int w, h;
public:
	Rectangle(int a, int b) : w(a), h(b) {}
	double area() override {
		return w * h;
	}
};
int main() {
	Circle c(3);
	Rectangle r(3, 4);
	cout << c.area() <<endl;
	cout << r.area();
}
```
# 4번
```cpp
#include<iostream>
template<typename T>
void swapValuse(T& a, T& b) {
	T temp = a;
	a = b;
	b = temp;
}
int main() {
	int a = 10, b = 20;
	std::cout << a << " " << b << std::endl;
	swapValuse(a, b);
	std::cout << a << " " << b << std::endl;
}
```

# 5번
```cpp
#include<iostream>
#include<fstream>
int main() {
	std::ofstream ofs("my.txt");
	ofs << "11\n" << "22";
	ofs.close();

	try {
		int a, b;
		std::ifstream ifs("my1.txt");
		ifs >> a >> b;
		if (!ifs) {
			throw "파일 오류";
		}
		std::cout << a << " " << b;
	}
	catch (const char* msg) {
		std::cerr << msg;
	}
}
```
# 6번
```cpp
#include<iostream>
#include<vector>
int main() {
	std::vector<int> v = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
	[v]() {
		for (auto a : v) {
			std::unique_ptr<int> p = std::make_unique<int>(a);
			if (*p % 2 == 0) {
				std::cout << *p << " ";
			}
		}
	}();
}
```
```cpp
#include<iostream>
int main() {
	auto fn  = []() {return 11 + 22;};
	std::cout << fn();
 }
```




















