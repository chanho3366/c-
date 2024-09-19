//#include <iostream>
//using namespace std;
//c++ 17p 
/*
int main()
{
    int val1;
    std::cout << "첫번째 숫자 입력: ";
    std::cin >> val1;

    int val2;
    std::cout << "두번째 숫자 입력: ";
    std::cin >> val2;

    int result = val1 + val2;
    std::cout << "덧셈 결과: " << result << std::endl;
    return 0;
}
*/


/*
//c++ 21p
int main(void)
{
    char name[200];
    char lang[200];

    std::cout << "이름은 무엇입니까? ";
    std::cin>>lang;

    std::cout << "내 이름은 " << name << "입니다\n";
    std::cout << "제일 좋아하는 언어는" << lang << "입니다" << std::endl;
    return 0;
}
*/

//c++ 25p
/*
void myfunc(void)
{
    std::cout << "myfunc(void) celled" << std::endl;
}
void myfunc(char c)
{
    std::cout << "myfunc(char c) celled" << std::endl;
}
void myfunc(int a,int b)
{
    std::cout << "myfunc(int a,int b) celled" << std::endl;
}
int main(void)
{
    myfunc();
    myfunc('A');
    myfunc(12,13);
    return 0;
}
*/

//c++ 26p
/*
int main(void)
{

    int num1 = 20, num2 = 30;
    swap(&num1, &num2);
    std::cout << num1 << ' ' << num2 << std::endl;

    char ch1 = 'a', ch2 = 'z';
    swap(&ch1, &ch2);
    std::cout << ch1 << ' ' << ch2 << std::endl;

    double dbl1 = 1.111, dbl2 = 5.555;
    swap(&dbl1, &dbl2);
    std::cout << dbl1 << ' ' << dbl2 << std::endl;
    return 0;
}
*/

/*
int adder(int num1 = 1, int num2 = 2);

int main(void)
{
    std::cout << adder() << std::endl;
    std::cout << adder(5) << std::endl;
    std::cout << adder(3,5) << std::endl;

}
int adder(int num1, int num2)
{
    return num1 + num2;
}
*/

/*
using namespace std;
int main(void)
{
    int num = 10;
    int i = 0;

    cout << "true: " << true << endl;
    cout << "false: " << false << endl;

    while (true)
    {
        cout << i++ << ' ';
        if (i > num)
            break;
    }
    cout << endl;

    cout << "sizeof 1: " << siezof(1) << endl;
    cout << "sizeof 0: " << siezof(0) << endl;
    cout << "sizeof true: " << siezof(true) << endl;
    cout << "sizeof false: " << siezof(false) << endl;
}
*/

/*
using namespace std;
int main(void)
{
    int arr[3] = { 1,3,5 };
    int& ref1 = arr[0];
    int& ref2 = arr[1];
    int& ref3 = arr[2];

    cout << ref1 << endl;
    cout << ref2 << endl;
    cout << ref3 << endl;

    return 0;
}
*/

/*
using namespace std;
void SwapByRef2(int& res1, int res2)
{
    int temp = res1;
    res1 = res2;
    res2 = temp;
}

int main(void)
{
    int val1 = 10;
    int val2 = 20;

    SwapByRef2(val1, val2);
    cout << "val1: " << val1 << endl;
    cout << "val2: " << val1 << endl;
    return 0;
}
*/


/*


#define ID_LEN 20
#define MAX_SPD 200
#define FUEL_STEP 2
#define ACC_STEP 10
#define BRK_STEP 10

struct car
{
    char gamerID[ID_LEN];
    int fuelGauge;
    int curSpeed;
};

void ShowCarStart()
{
    cout << "소유자ID: " << gamerID << endl;
    cout << "연료량: " << fuelGauge <<'%' << endl;
    cout << "현재속도: " << curSpeed << "km/s" << endl;
}

void accel()
{
    if (fuelGauge <= 0)
        return;
    else
        fuelGauge -= FUEL_STEP;

    if (curspeed + ACC_STEP >= MAX_SPD)
    {
        curspeede
    }
}



*/

/*
#include <iostream>
using namespace std;

#define ID_LEN 20
#define MAX_SPD 200
#define FUEL_STEP 2
#define ACC_STEP 10
#define BRK_STEP 10

#include <cstring>

struct Car
{
    char gamerID[ID_LEN];
    int fuelGauge;
    int curSpeed;

    void Accel() {
        if (fuelGauge <= 0) return;
        else fuelGauge -= FUEL_STEP;
        if (curSpeed + ACC_STEP >= MAX_SPD) {
            curSpeed = MAX_SPD;
            return;
        }
        curSpeed += ACC_STEP;
    }

    void Break() {
        if (curSpeed < BRK_STEP) {
            curSpeed = 0;
            return;
        }
        curSpeed -= BRK_STEP;
    }

    void ShowCarState() const { // 상수 함수
        curSpeed;
    }

    Car(const char* gamerID, int fuelGuage, int curSpeed) {
        strcpy(this->gamerID, gamerID);
        this->fuelGauge = fuelGuage;
        this->curSpeed = curSpeed;
        cout << "construct called" << endl;
    }
};

//#include <cstring>
//
//void init(Car &car, const char * gamerID, int fuelGuage, int curSpeed) {
//   strcpy(car.gamerID,gamerID);
//   car.fuelGauge=fuelGuage;
//   car.curSpeed=curSpeed;
//}

int main(void) {
    //   Car run99={"run99",100,0}; // 방법 1
    //   Car run99; // 방법 1 - 생성
    //   strcpy(run99.gamerID, "run99"); - 초기화
    //   run99.fuelGauge=100; - 초기화
    //   run99.curSpeed=0; - 초기화
    //   Car run99; // 생성
    //   init(run99,"run99",100,0); // 초기화
    Car run99("run99", 100, 0);

    run99.curSpeed = 50;
    run99.Accel();
    run99.Accel();
    run99.ShowCarState();
    run99.Break();
    run99.ShowCarState();

    //   Car sped77={"sped77",100,0};
    Car sped77("sped77", 100, 0);
    sped77.Accel();
    sped77.Break();
    sped77.ShowCarState();

    return 0;
}
*/
/*

//#include <iostream>
using namespace std;

#define ID_LEN 20
#define MAX_SPD 200
#define FUEL_STEP 2
#define ACC_STEP 10
#define BRK_STEP 10

struct car
{
    char gamerID[ID_LEN];
    int fuelGauge;
    int curSpeed;
};

void ShowCarStart(car c)  // car 객체를 매개변수로 받도록 수정
{
    cout << "소유자ID: " << c.gamerID << endl;
    cout << "연료량: " << c.fuelGauge << '%' << endl;
    cout << "현재속도: " << c.curSpeed << "km/s" << endl;
}

void accel(car c)
{
    if (c.fuelGauge <= 0)
        return;
    else
        c.fuelGauge -= FUEL_STEP;

    if (c.curSpeed + ACC_STEP >= MAX_SPD)
    {
        c.curSpeed;
    }
}
*/


/*
#ifdef __CAR_H__
#define __CAR_H__
namespace car_const {

    enum {
        id_len = 20,max_speed
    };
};

namespace car
{
private:
    char gmaeid[car_const::id_len]
}



#endif


*/

/*
#ifndef __CARINLINE_H__
#define __CARINLINE_H__
#include<iostream>
using namespace std;
namespace CAR_CONST
{
    enum
    {
        ID_LEN = 20, MAX_SPD = 200, FULL_STEP = 2, ACC_STEP = 10, BRK_STEP = 10
    };
}


class car
{
private:
    char gmaerID[CAR_CONST::ID_LEN];
    int fuelGauge;
    int curSpeed;
public:
    void InitMembers(char* ID, int fuel);
    void ShowCarState();
    void Accel();
    void break();

};

inline void car::ShowCarState()
{
    cout << "사용자ID: " << gamerID << endl;
    cout << "연료량: " << fuelGauge <<"%" << endl;
    cout << "현재속도: " << curSpeed <<"km/s" << endl;
}

inline void car::Break()
{
    if(curSpeed<CAR_CONST::BRK_STEPaaa)
}

#endif // 
*/

/*
class Circle {
private:
    Point center;
    int radius;
public:
    void Init(int x, int y, int r) {
        center.Init(x, y);
        radius = r;

    }
    void ShowCircleInfo() {
        cout << "radius: " << radius << endl;
        center.ShowPointInfo();
    }
};

class Ring {
private:
    Circle inner;
    Circle outer;
public:
    void Init(int x1, int y1, int r1, int x2, int y2, int r2) {
        inner.Init(x1, y1, r1);
        outer.Init(x2, y2, r2);
    }
    void ShowRingInfo() {
        cout << "Inner Circle Info..." << endl;
        inner.ShowCircleInfo();
        cout << "Outter Circle Info..." << endl;
        outer.ShowCircleInfo();
    }
};

*/

/*
#include <iostream>
#include <cstring>

using namespace std;

class person
{
private:
    char* name;
    int age;

public:
    person(char* myname, int myage);
    {
        int len = strlen(myname) + 1;
        name = new char[len];
        strcpy(name, myname);
        age = myage;
    }
    void ShowPersonInfo() const
    {
        cout << "이름: " << name << endl;
        cout << "나이: " << age << endl;
    }
    ~person()
    {
        delete[]name;
        cout << "called destruetor!" << endl;
    }
};

int main(void)
{
    person man1("Lee dong woo", 29);
    person man2("jang dong gun", 41);
    man1.ShowPersonInfo();
    man2.ShowPersonInfo();

    return 0;
}

*/
/*
#include <iostream>
using namespace std;
class Person
{
public:
    Person()
    {
        cout << "1 " << this << endl;
    }
    void id()
    {
        cout << "2 " << this << endl;
    }
};

int main()
{
    Person& p1 = *new Person();
    p1.id();
    cout << "3 " << &p1 << endl;

    Person& p2 = *new Person();
    p2.id();
    cout << "3 " << &p2 << endl;
}
*/


/*#include <cstring>
#include <iostream>

using namespace std;

namespace COMP_POS
{
    enum
    {
        CLERK,
        SENIOR,
        ASSIST,
        MANAGER
    };
}

class NameCard
{
    char *name;
    char *company;
    char *phone;
    int role;

public:
    NameCard(const char *name, const char *company, const char *phone, int role)
    {
        int name_len = strlen(name) + 1;
        this->name = new char[name_len];
        strcpy(this->name, name);
        int company_len = strlen(company) + 1;
        this->company = new char[company_len];
        strcpy(this->company, company);
        int phone_len = strlen(콜) + 1;
        this->phone = new char[phone_len];
        strcpy(this->phone, phone);
        this->role = role;
    }
    ~NameCard()
    {
        delete[] name;
        delete[] company;
        delete[] phone;
    }
    void ShowNameCardInfo(void)
    {
        cout << "이름:" << name << endl;
        cout << "회사:" << company << endl;
        cout << "전화번호:" << phone << endl;
        cout << "직급:" << strRole() << endl;
    }
    const char *strRole()
    {
        const char *str_role =
            role == COMP_POS::CLERK ? "사원" : role == COMP_POS::SENIOR ? "주임"
                                           : role == COMP_POS::ASSIST   ? "대리"
                                                                        : "과장";
        return str_role;
    }
};

int main()
{
    NameCard &manClerk = *new NameCard("Lee", "ABCEng", "010-1111-2222", COMP_POS::CLERK);
    manClerk.ShowNameCardInfo();
    delete &manClerk;
}*/

/*
#include <iostream>
using namespace std;
class Person {
};
void PersonInit(Person* THIS) {
    cout << "1 " << THIS << endl;
}
void id(Person* THIS) {
    cout << "2 " << THIS << endl;
}

int main() {
    Person& p1 = *new Person();
    PersonInit(&p1);
    id(&p1);
    cout << "3 " << &p1 << endl;
}
*/
/*
int main()
{
    char carr1[10] = "hello";
    int i1 = 1;
    int i2 = 2;

    CArr ca1 = { "hello" };
    CArr ca2 = ca1;

    cout << ca2.carr << endl;

    i2 = i1;
    ca2 = ca1;
    cout << ca2.carr << endl;
}
*/


/*
#include <iostream>
#include <cstring>
using namespace std;

class Book
{
private:
    char* title;
    char* isbn;
    int price;

public:
    Book(const char* title, const char* isbn, int price)
    {
        int tlen = strlen(title) + 1;
        this->title = new char[tlen];
        strcpy(this->title, title);
        int ilen = strlen(isbn) + 1;
        this->isbn = new char[ilen];
        strcpy(this->isbn, isbn);
        this->price = price;
    }
    Book(const Book& br)
    {
        int tlen = strlen(br.title) + 1;
        this->title = new char[tlen];
        strcpy(this->title, br.title);
        int ilen = strlen(br.isbn) + 1;
        this->isbn = new char[ilen];
        strcpy(this->isbn, br.isbn);
        this->price = br.price;
    }
    Book()
    {
        title = NULL;
        isbn = NULL;
        price = 0;
    }
    void operator=(const Book& br)
    {
        if (title != NULL)
            delete[] title;
        if (isbn != NULL)
            delete[] isbn;
        int tlen = strlen(br.title) + 1;
        this->title = new char[tlen];
        strcpy(this->title, br.title);
        int ilen = strlen(br.isbn) + 1;
        this->isbn = new char[ilen];
        strcpy(this->isbn, br.isbn);
        this->price = br.price;
    }
    ~Book()
    {
        delete[] this->title;
        delete[] this->isbn;
    }
    void ShowBookInfo()
    {
        cout << "제목: " << title << endl;
        cout << "ISBN: " << isbn << endl;
        cout << "가격: " << price << endl;
    }
};
class EBook : public Book
{
private:
    char* DRMKey;

public:
    EBook(const char* title, const char* isbn, int price, const char* DRMKey) : Book(title, isbn, price)
    {
        int dlen = strlen(DRMKey) + 1;
        this->DRMKey = new char[dlen];
        strcpy(this->DRMKey, DRMKey);
    }
    EBook(const EBook& ebr) : Book(ebr)
    {
        int dlen = strlen(DRMKey) + 1;
        DRMKey = new char[dlen];
        strcpy(DRMKey, DRMKey);
    }
    EBook() : Book()
    {
        DRMKey = NULL;
    }
    void operator=(const EBook& ebr)
    {
        Book::operator=(ebr);
        if (DRMKey != NULL)
            delete[] DRMKey;
        int dlen = strlen(ebr.DRMKey) + 1;
        DRMKey = new char[dlen];
        strcpy(DRMKey, ebr.DRMKey);
    }
    ~EBook()
    {
        delete[] DRMKey;
    }
    void ShowEBookInfo()
    {
        ShowBookInfo();
        cout << "인증키: " << DRMKey << endl;
    }
};

int main()
{
    Book book("좋은 C++", "555-12345-890-0", 20000);
    book.ShowBookInfo();
    cout << endl;
    EBook ebook("좋은 C++ ebook", "555-12345-890-1", 10000, "fdx9w");
    ebook.ShowEBookInfo();
}
*/

/*
#include <iostream>
using namespace std;
class Character
{
public:
    virtual void play() {}
};
class Worrior : public Character
{
public:
    void play() { cout << "전사 공격" << endl; }
};
class Magician : public Character
{
public:
    void play() { cout << "마법사 공격" << endl; }
};
class GameManager
{
    Character& ch1;
    Character& ch2;

public:
    GameManager(Character& ch1, Character& ch2) : ch1(ch1), ch2(ch2) {}
    void run()
    {
        ch1.play();
        ch2.play();
    }
};
int main()
{
    GameManager manager(*new Worrior, *new Magician);
    manager.run();
}
*/
/*
#include <iostream>

using namespace std;

class aaa
{
private:
    int num1;

public:
    virtual void func1() { cout << "func1" << endl; }
    virtual void func2() { cout << "func2" << endl; }
};

class bbb : public aaa
{
private:
    int num2;
public:
    virtual void func1() { cout << "bbb:func1" << endl; }
    void func3() { cout << func3 << endl; }
};

void main(void)
{
    aaa* aptr = new aaa();
    aptr->func1();
    
    bbb* bptr = new bbb();
    bptr->func1();

    return 0;
}
*/

/*

#include <iostream>
using namespace std;
class Point {
    int x, y;
public:
    Point(int x, int y) :x(x), y(y) {}
    Point& operator+(const Point& pt2) const {
        cout << "operator+" << endl;
        int x3 = this->x + pt2.x;
        int y3 = this->y + pt2.y;
        cout << x3 << endl;
        cout << y3 << endl;
        Point& pt3 = *new Point(x3, y3);
        return pt3;
        // return Point(x3,y3);
    }
    Point& operator++() {
        cout << "operator++" << endl;
        ++x; ++y;
        cout << x << endl; cout << y << endl;
        return *this;
    }
    // Point operator++(int) { // case 1
    // Point& operator++(int) { // case 2
    Point&& operator++(int) {
        cout << "operator++(int)" << endl;
        int tx = this->x;
        int ty = this->y;
        this->x++; this->y++;
        // return Point(tx,ty); // case 1
        // return *new Point(tx,ty); // case 2
        return Point(tx, ty);
    }
};
int main() {
    int num1 = 1, num2 = 2;
    int num3 = num1 + num2;
    cout << num3 << endl;
    Point point1(1, 1), point2(2, 2);
    // Point point3(0, 0);
    //  point3=point1+point2;
    Point& point3 = point1 + point2;
    // point1.operator+(point2)
    // point3.operator=(point1.operator+(point2))
    ++(++num1); // num1=num1+1
    ++(++point1);
    // point1.operaotr++()
    num2 = num1++;
    point2 = point1++;
    // point1.operator++(int)
    Point&& ptmp = point1++;
    // point2=ptmp;
    // delete &ptmp;
}

*/


/*
#include <iostream>

using namespace std;

class point
{
private:
    int xpos, ypos;
public:
    point(int x=0,int y=0) : xpos(x),ypos(y)
    {}
    void showposition() const
    {
        cout << '[' << xpos << ", " << ypos << ']' << endl;

    }
};
*/
/*
#include <iostream>
#include <string>
using namespace std;

class Tv
{
public:
    bool power;
    int channel;
    Tv(bool power, int channel)
    {
        this->power = power;
        this->channel = channel;
    }
    void powerOnOff() { power = !power; }
    void channelUp() { ++channel; }
    void channelDown() { --channel; }
};
class SmartTv : public Tv
{
public:
    bool caption;
    SmartTv(bool power, int channel) : Tv(power, channel) {}
    void displayCaption(string& text)
    {
        if (caption)
        {
            cout << text << endl;
        }
    }
};

int main(int argc, char** argv)
{
    SmartTv& stv = *new SmartTv(false, 1);
    stv.channel = 10;
    stv.channelUp();
    stv.displayCaption(*new string("Hello, World"));
    stv.caption = true;
    stv.displayCaption(*new string("Hello, World"));
}*/



#include <iostream>
using namespace std;
class Weapon {
public: virtual void attack() = 0; // 순수 virtual함수(추상 클래스)
};
class Sword : public Weapon {
public: void attack() { cout << "검" << endl; }
};
class Axe : public Weapon {
public: void attack() { cout << "도끼" << endl; }
};
class Worrior {
    Weapon* weapon;
public:
    void getWeapon(Weapon* weapon) {
        this->weapon = weapon;
    }
    void attack() {
        weapon->attack();
    }
};
int main()
{
    Worrior& worrior = *new Worrior();
    worrior.getWeapon(new Sword());
    worrior.attack();
    worrior.getWeapon(new Axe());
    worrior.attack();
}
