---
title: "변경 사항 개요(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 변경 사항 개요(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 개요에서는 Managed Extensions for C\+\+와 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]의 언어 변경 사항 중 일부에 대한 예제를 보여 줍니다.  자세한 내용은 각 항목의 해당 링크를 참조하십시오.  
  
## 두 개의 밑줄이 있는 키워드 사용 안 함  
 하나의 예외를 제외하고 모든 키워드 앞에 나오는 두 개의 밑줄이 제거되었습니다.  따라서 `__value`는 `value`가 되고 `__interface`는 `interface`가 됩니다.  사용자 코드의 식별자와 키워드 간에 이름이 충돌하지 않게 하기 위해 키워드는 주로 상황에 맞게 처리됩니다.  
  
 자세한 내용은 [언어 키워드\(C\+\+\/CLI\)](../dotnet/language-keywords-cpp-cli.md)를 참조하십시오.  
  
## 클래스 선언  
 Managed Extensions 구문  
  
```  
__gc class Block {};                           // reference class  
__value class Vector {};                       // value class  
__interface I {};                        // interface class  
__gc __abstract class Shape {};                // abstract class  
__gc __sealed class Shape2D : public Shape {}; // derived class  
```  
  
 새 구문  
  
```  
ref class Block {};                // reference class  
value class Vector {};             // value class  
interface class I {};        // interface class  
ref class Shape abstract {};       // abstract class  
ref class Shape2D sealed: Shape{}; // derived class  
```  
  
 자세한 내용은 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)를 참조하십시오.  
  
## 개체 선언  
 Managed Extensions 구문  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   System::Windows::Forms::Button   __gc *button1;  
   System::Windows::Forms::DataGrid __gc *myDataGrid;     
   System::Data::DataSet  __gc *myDataSet;  
};  
```  
  
 새 구문  
  
```  
public ref class Form1 : System::Windows::Forms::Form {  
   System::ComponentModel::Container^ components;  
   System::Windows::Forms::Button^ button1;  
   System::Windows::Forms::DataGrid^ myDataGrid;  
   System::Data::DataSet^ myDataSet;  
};  
```  
  
 자세한 내용은 [CLR 참조 클래스 개체 선언](../dotnet/declaration-of-a-clr-reference-class-object.md)를 참조하십시오.  
  
### 관리되는 힙 할당  
 Managed Extensions 구문  
  
```  
Button* button1 = new Button; // managed heap  
int *pi1 = new int;           // native heap  
Int32 *pi2 = new Int32;       // managed heap  
```  
  
 새 구문  
  
```  
Button^ button1 = gcnew Button;        // managed heap  
int * pi1 = new int;                   // native heap  
Int32^ pi2 = gcnew Int32;              // managed heap  
```  
  
 자세한 내용은 [CLR 참조 클래스 개체 선언](../dotnet/declaration-of-a-clr-reference-class-object.md)를 참조하십시오.  
  
### 어떠한 개체도 가리키지 않는 추적 참조  
 Managed Extensions 구문  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 새 구문  
  
```  
// Incorrect Translation  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
  
// Correct Translation  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to an Int32^  
Object ^ obj2 = 1;  
```  
  
 자세한 내용은 [CLR 참조 클래스 개체 선언](../dotnet/declaration-of-a-clr-reference-class-object.md)를 참조하십시오.  
  
## 배열 선언  
 CLR 배열이 다시 디자인되었습니다.  이는 stl `vector` 템플릿 컬렉션과 비슷하지만 내부 `System::Array` 클래스에 매핑되므로 템플릿 구현은 아닙니다.  
  
 자세한 내용은 [CLR 배열 선언](../dotnet/declaration-of-a-clr-array.md)를 참조하십시오.  
  
### 배열을 매개 변수로 사용  
 Managed Extensions 배열 구문  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 새 배열 구문  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### 배열을 반환 형식으로 사용  
 Managed Extensions 배열 구문  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 새 배열 구문  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### 로컬 CLR 배열의 약식 초기화  
 Managed Extensions 배열 구문  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),  
                                 __box(29), __box(30) };  
  
   return a1;  
}  
```  
  
 새 배열 구문  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
  
   return a1;  
}  
```  
  
### 명시적 CLR 배열 선언  
 Managed Extensions 배열 구문  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 새 배열 구문  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 새로운 언어 기능: gcnew 다음에 오는 명시적 배열 초기화  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## 스칼라 속성  
 Managed Extensions 속성 구문  
  
```  
public __gc __sealed class Vector {  
   double _x;  
  
public:  
   __property double get_x(){ return _x; }  
   __property void set_x( double newx ){ _x = newx; }  
};  
```  
  
 새 속성 구문  
  
```  
public ref class Vector sealed {   
   double _x;  
  
public:  
   property double x   
   {  
      double get()             { return _x; }  
      void   set( double newx ){ _x = newx; }  
   } // Note: no semi-colon …  
};  
```  
  
 새로운 언어 기능: trivial 속성  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 자세한 내용은 [속성 선언](../dotnet/property-declaration.md)를 참조하십시오.  
  
## 인덱싱된 속성  
 Managed Extensions 인덱싱된 속성 구문  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 새 인덱싱된 속성 구문  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 새로운 언어 기능: 클래스 수준의 인덱싱된 속성  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 자세한 내용은 [속성 인덱스 선언](../dotnet/property-index-declaration.md)를 참조하십시오.  
  
## 오버로드된 연산자  
 Managed Extensions 연산자 오버로드 구문  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
};  
  
int main() {  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc = Vector::op_Division( pa, 4.8916 );  
  
   if ( Vector::op_Equality( pa, pc ))  
      ;  
}  
```  
  
 새 연산자 오버로드 구문  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
};  
  
int main() {  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );  
  
   Vector^ pc = pa / 4.8916;  
   if ( pc == pa )  
      ;  
}  
```  
  
 자세한 내용은 [오버로드된 연산자](../dotnet/overloaded-operators.md)를 참조하십시오.  
  
## 변환 연산자  
 Managed Extensions 변환 연산자 구문  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 새 변환 연산자 구문  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 자세한 내용은 [변환 연산자의 변경 내용](../dotnet/changes-to-conversion-operators.md)를 참조하십시오.  
  
## 인터페이스 멤버 명시적 재정의  
 Managed Extensions 명시적 재정의 구문  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 새 명시적 재정의 구문  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 자세한 내용은 [인터페이스 멤버 명시적 재정의](../dotnet/explicit-override-of-an-interface-member.md)를 참조하십시오.  
  
## 전용 가상 함수  
 Managed Extensions 전용 가상 함수 구문  
  
```  
__gc class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
__gc class Derived : public Base {  
public:  
   // ok: g() overrides Base::g()  
   virtual void g();  
};  
```  
  
 새 전용 가상 함수 구문  
  
```  
ref class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
ref class Derived : public Base {  
public:  
   // error: cannot override: Base::g() is inaccessible  
   virtual void g() override;  
};  
```  
  
 자세한 내용은 [전용 가상 함수](../dotnet/private-virtual-functions.md)를 참조하십시오.  
  
## CLR 열거형 형식  
 Managed Extensions 열거형 구문  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};    
```  
  
 새 열거형 구문  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 이와 같은 구문 상의 작은 변화 이외에도 CLR 열거형 형식의 동작이 여러 측면에서 변경되었습니다.  
  
-   CLR 열거형의 전방 선언이 더 이상 지원되지 않습니다.  
  
-   기본 제공 산술 형식과 Object 클래스 계층 구조 사이의 오버로드 확인이 Managed Extensions와 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 사이에서 서로 뒤바뀌었습니다.  이로 인해 CLR 열거형이 더 이상 암시적으로 산술 형식으로 변환되지 않는 부작용이 있습니다.  
  
-   새 구문에서는 Managed Extensions에서와 달리 CLR 열거형이 자체 범위를 유지합니다.  이전에는 열거형을 포함하는 범위에서 열거자를 볼 수 있었지만 이제는 열거자가 열거형의 범위 내에서 캡슐화됩니다.  
  
 자세한 내용은 [CLR 열거형 형식](../dotnet/clr-enum-type.md)를 참조하십시오.  
  
## \_\_box 키워드 제거  
 Managed Extensions boxing 구문  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 새 boxing 구문  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 자세한 내용은 [boxed 값에 대한 추적 핸들](../dotnet/a-tracking-handle-to-a-boxed-value.md)를 참조하십시오.  
  
## 고정 포인터  
 Managed Extensions 고정 포인터 구문  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 새 고정 포인터 구문  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 자세한 내용은 [값 형식 의미](../dotnet/value-type-semantics.md)를 참조하십시오.  
  
## \_\_typeof 키워드 대신 typeid 사용  
 Managed Extensions typeof 구문  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 새 typeid 구문  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 자세한 내용은 [typeof 대신 T::typeid 사용](../dotnet/typeof-goes-to-t-typeid.md)를 참조하십시오.  
  
## 참고 항목  
 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)   
 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ko-kr/edbded88-7ef3-4757-bd9d-b8f48ac2aada)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)