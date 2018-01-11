---
title: "변경 사항 개요 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fdc0015bda5f0a6678b1d274c79445aba4e4aab0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="outline-of-changes-ccli"></a>변경 사항 개요(C++/CLI)
이 개요 예를 보여 줍니다 하면 일부 변경 Managed Extensions에서 언어의 Visual c + + c + +에 대 한 합니다. 자세한 내용은 각 항목을 함께 제공 되는 링크를 따라 이동 합니다.  
  
## <a name="no-double-underscore-keywords"></a>두 개의 밑줄 키워드 없음  
 한 가지 예외로 모든 키워드 앞에 이중 밑줄, 없어졌습니다. 따라서 `__value` 됩니다 `value`, 및 `__interface` 되 `interface`등입니다. 키워드와 사용자 코드에서 식별자 간의 이름 충돌을 방지 하려면 키워드 상황에 맞게 처리 주로 됩니다.  
  
 참조 [언어 키워드 (C + + /cli CLI)](../dotnet/language-keywords-cpp-cli.md) 자세한 정보에 대 한 합니다.  
  
## <a name="class-declarations"></a>클래스 선언  
 관리 되는 확장 구문을 사용 하십시오.  
  
```  
__gc class Block {};                           // reference class  
__value class Vector {};                       // value class  
__interface I {};                        // interface class  
__gc __abstract class Shape {};                // abstract class  
__gc __sealed class Shape2D : public Shape {}; // derived class  
```  
  
 새 구문:  
  
```  
ref class Block {};                // reference class  
value class Vector {};             // value class  
interface class I {};        // interface class  
ref class Shape abstract {};       // abstract class  
ref class Shape2D sealed: Shape{}; // derived class  
```  
  
 참조 [관리 되는 형식 (C + + /cli CL)](../dotnet/managed-types-cpp-cl.md) 자세한 정보에 대 한 합니다.  
  
## <a name="object-declaration"></a>개체 선언  
 관리 되는 확장 구문을 사용 하십시오.  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   System::Windows::Forms::Button   __gc *button1;  
   System::Windows::Forms::DataGrid __gc *myDataGrid;     
   System::Data::DataSet  __gc *myDataSet;  
};  
```  
  
 새 구문:  
  
```  
public ref class Form1 : System::Windows::Forms::Form {  
   System::ComponentModel::Container^ components;  
   System::Windows::Forms::Button^ button1;  
   System::Windows::Forms::DataGrid^ myDataGrid;  
   System::Data::DataSet^ myDataSet;  
};  
```  
  
 참조 [CLR 참조 클래스 개체의 선언](../dotnet/declaration-of-a-clr-reference-class-object.md) 자세한 정보에 대 한 합니다.  
  
### <a name="managed-heap-allocation"></a>관리 되는 힙 할당  
 관리 되는 확장 구문을 사용 하십시오.  
  
```  
Button* button1 = new Button; // managed heap  
int *pi1 = new int;           // native heap  
Int32 *pi2 = new Int32;       // managed heap  
```  
  
 새 구문:  
  
```  
Button^ button1 = gcnew Button;        // managed heap  
int * pi1 = new int;                   // native heap  
Int32^ pi2 = gcnew Int32;              // managed heap  
```  
  
 참조 [CLR 참조 클래스 개체의 선언](../dotnet/declaration-of-a-clr-reference-class-object.md) 자세한 정보에 대 한 합니다.  
  
### <a name="a-tracking-reference-to-no-object"></a>없는 개체에 대 한 추적 참조  
 관리 되는 확장 구문을 사용 하십시오.  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 새 구문:  
  
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
  
 참조 [CLR 참조 클래스 개체의 선언](../dotnet/declaration-of-a-clr-reference-class-object.md) 자세한 정보에 대 한 합니다.  
  
## <a name="array-declaration"></a>배열 선언  
 CLR 배열은 다시 디자인 되었습니다. Stl 비슷합니다 `vector` 템플릿 컬렉션 하지만 기본 지도 `System::Array` 클래스 즉, 되지 않습니다.-템플릿 구현 합니다.  
  
 참조 [CLR 배열 선언](../dotnet/declaration-of-a-clr-array.md) 자세한 정보에 대 한 합니다.  
  
### <a name="array-as-parameter"></a>배열을 매개 변수로  
 관리 되는 확장 배열 구문을 사용 하십시오.  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 새 배열 구문  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### <a name="array-as-return-type"></a>반환 형식으로 배열  
 관리 되는 확장 배열 구문을 사용 하십시오.  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 새 배열 구문  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### <a name="shorthand-initialization-of-local-clr-array"></a>로컬 CLR 배열의 약식 초기화  
 관리 되는 확장 배열 구문을 사용 하십시오.  
  
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
  
### <a name="explicit-clr-array-declaration"></a>명시적 CLR 배열 선언  
 관리 되는 확장 배열 구문을 사용 하십시오.  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 새 배열 구문  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 새로운 언어: gcnew를 뒤에 오는 명시적 배열 초기화  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## <a name="scalar-properties"></a>스칼라 속성  
 관리 되는 확장 속성 구문:  
  
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
   } // Note: no semi-colon  
};  
```  
  
 새로운 언어: trivial 속성  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 참조 [속성 선언](../dotnet/property-declaration.md) 자세한 정보에 대 한 합니다.  
  
## <a name="indexed-properties"></a>인덱싱된 속성  
 관리 되는 확장 속성 구문이 인덱싱됩니다.  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 새로운 인덱싱된 속성 구문:  
  
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
  
 새로운 언어: 클래스 수준 인덱싱된 속성  
  
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
  
 참조 [속성 인덱스 선언](../dotnet/property-index-declaration.md) 자세한 정보에 대 한 합니다.  
  
## <a name="overloaded-operators"></a>오버로드된 연산자  
 관리 되는 확장명 연산자 오버 로드 구문:  
  
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
  
 새 연산자 오버 로드 구문  
  
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
  
 참조 [오버 로드 된 연산자](../dotnet/overloaded-operators.md) 자세한 정보에 대 한 합니다.  
  
## <a name="conversion-operators"></a>변환 연산자  
 관리 되는 확장 변환 연산자 구문  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 새 변환 연산자 구문:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 참조 [변환 연산자를 변경](../dotnet/changes-to-conversion-operators.md) 자세한 정보에 대 한 합니다.  
  
## <a name="explicit-override-of-an-interface-member"></a>인터페이스 멤버 명시적 재정의  
 관리 되는 확장 명시적 재정의 구문:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 새 명시적 재정의 구문은:  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 참조 [인터페이스 멤버 명시적 재정의](../dotnet/explicit-override-of-an-interface-member.md) 자세한 정보에 대 한 합니다.  
  
## <a name="private-virtual-functions"></a>전용 가상 함수  
 관리 되는 확장 전용 가상 함수 구문:  
  
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
  
 참조 [개인 가상 함수](../dotnet/private-virtual-functions.md) 자세한 정보에 대 한 합니다.  
  
## <a name="clr-enum-type"></a>CLR 열거형 형식  
 관리 되는 확장 열거형 구문  
  
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
  
 이 작은 구문 변경 외에도 여러 가지 방법으로 CLR 열거형 형식의 동작이 변경 되었습니다.  
  
-   CLR 열거형의 정방향 선언 더 이상 지원 합니다.  
  
-   Managed Extensions 사이의 Visual c + + 기본 제공 산술 형식 및 개체 클래스 계층 구조 사이의 오버 로드 확인이 바뀌었습니다. 파생 작업으로 CLR 열거형 산술 형식으로 더 이상 암시적으로 변환 됩니다.  
  
-   새 구문에서 CLR 열거형에는 그렇지 않은 경우 관리 되는 확장에는 자체 범위를 유지 관리 합니다. 이전에 열거자는 열거형; 포함 하는 범위 내에 표시 되었습니다. 이제, 열거자가 열거형의 범위 내에서 캡슐화 됩니다.  
  
 참조 [CLR 열거형 형식](../dotnet/clr-enum-type.md) 자세한 정보에 대 한 합니다.  
  
## <a name="removal-of-box-keyword"></a>__Box 키워드 제거  
 관리 되는 확장 boxing 구문:  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 새 한 boxing 구문:  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 참조 [A 추적 Boxed 값에 대 한 핸들](../dotnet/a-tracking-handle-to-a-boxed-value.md) 자세한 정보에 대 한 합니다.  
  
## <a name="pinning-pointer"></a>고정 포인터  
 관리 되는 확장 프로그램을 고정 포인터 구문:  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 새 고정 포인터 구문:  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 참조 [값 형식 의미](../dotnet/value-type-semantics.md) 자세한 정보에 대 한 합니다.  
  
## <a name="typeof-keyword-becomes-typeid"></a>__typeof 키워드는 typeid  
 관리 되는 확장 typeof 구문을 사용 하십시오.  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 새 typeid 구문:  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 참조 [Typeof T::typeid](../dotnet/typeof-goes-to-t-typeid.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + /CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)   
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)


