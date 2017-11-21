---
title: "CLR 참조 클래스 개체의 선언 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 973500cc276d95e523859a5fcc1b9a5f7a707bb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="declaration-of-a-clr-reference-class-object"></a>CLR 참조 클래스 개체 선언
선언 하 고 참조 클래스 형식의 개체를 인스턴스화하는 구문 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 Managed Extensions 참조 클래스 형식 개체의 선택적으로 사용 하도록 함께 ISO c + + 포인터 구문을 사용 하 여 선언 된는 `__gc` 별의 왼쪽에는 키워드 (`*`). 예를 들어 다음은 참조의 다양 한 클래스 형식 개체 선언 Managed Extensions 구문:  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   Button __gc *button1;  
   DataGrid __gc *myDataGrid;     
   DataSet __gc *myDataSet;  
  
   void PrintValues( Array* myArr ) {  
      System::Collections::IEnumerator* myEnumerator =   
         myArr->GetEnumerator();  
  
      Array *localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);  
   }  
};  
```  
  
 새 구문에서 새로운 선언적 토큰을 사용 하 여 참조 클래스 형식 개체 선언 (`^`) 라고 공식적으로 *추적 핸들* 으로 보다 쉽게 이야기는 *hat*합니다. (추적 형용사 참조 형식에서 CLR 힙으로부터 수 자동으로 옮길 위치 하는 동안 가비지 수집 힙의 압축을 의미 합니다. 런타임 동안 추적 핸들 업데이트 투명 하 게 됩니다. 비슷한 두 가지 개념인는 *추적 참조* (`%`), 및 *내부 포인터* (`interior_ptr<>`)에 대 한 자세한 내용은 [값 형식 의미](../dotnet/value-type-semantics.md)합니다.  
  
 ISO c + + 포인터 구문을 재사용 서 선언 구문을 이동 하는 주된 이유는 다음과 같습니다.  
  
-   포인터 구문을 사용 하 여 참조 방식 개체를 직접 적용 하는 오버 로드 된 연산자를 허용 하지 않았습니다. 같은 내부 이름을 사용 하 여 연산자를 호출 해야 했습니다 하나는 대신, `rV1->op_Addition(rV2)` 보다 직관적인 대신 `rV1+rV2`합니다.  
  
-   힙을 수집 하는 다양 한 포인터 산술 연산, 캐스팅 등 포인터 연산에 대 한 가비지에 저장 된 개체에 대 한 허용 되지 않습니다. 더 나은 추적 핸들의 개념은 CLR 참조 형식의 특성을 캡처합니다.  
  
 `__gc` 한정자 추적 핸들에 필요 하지 않으며 지원 되지 않습니다. 자체 개체를 사용 하는 변경 되지 않습니다. 멤버 포인터 멤버 선택 연산자를 통해 여전히 액세스 (`->`). 예를 들어 다음은 새 구문으로 변환 이전 Managed Extensions 코드 샘플입니다.  
  
```  
public ref class Form1: public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container^ components;  
   Button^ button1;  
   DataGrid^ myDataGrid;  
   DataSet^ myDataSet;  
  
   void PrintValues( Array^ myArr ) {  
      System::Collections::IEnumerator^ myEnumerator =  
         myArr->GetEnumerator();  
  
      Array ^localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);   }  
};  
```  
  
## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>CLR 힙에 있는 개체의 동적 할당  
 Managed extensions에서 두 개의 존재 `new` 네이티브 및 관리 되는 힙 간에 할당 하는 식 대부분 투명 하 게 되었습니다. 거의 모든 경우에는 컴파일러는 네이티브 또는 관리 되는 힙에서 메모리를에서 할당 여부를 결정 하는 컨텍스트를 사용할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 원하지 않는 상황에 맞는 힙 할당을 사용 하 여 컴파일러 지시할 수 있습니다는 `__gc` 또는 `__nogc` 키워드입니다. 새 구문에서 두 개의 새 식의 개별 특성이 명확 하 게 드러납니다의 도입으로는 `gcnew` 키워드입니다. 예를 들어 새 구문에서 위의 세 가지 선언은 다음과 같이 표시.  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 다음은 Managed Extensions 초기화는 `Form1` 이전 섹션에서 선언 된 멤버:  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 새 구문으로 다시 캐스팅 같은 초기화는 다음과 같습니다. 대상의 경우에 hat 참조 형식에 대 한 필요 하지 않습니다는 `gcnew` 식입니다.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## <a name="a-tracking-reference-to-no-object"></a>없는 개체에 대 한 추적 참조  
 새 구문에서 `0` 더 이상 null 주소를 나타내지 않으며 동일 정수로 처리 `1`, `10`, 또는 `100`합니다. 새 특별 한 토큰에는 추적 참조에 대 한 null 값을 나타냅니다. 예를 들어 관리 되는 확장에 없는 개체를 다음과 같이 주소를 지정 하는 참조 형식 초기화:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 새 구문에서 초기화 또는 할당 된 값의 형식에 `Object` 하면 해당 값 형식의 암시적 boxing 합니다. 새 구문에서 모두 `obj` 및 `obj2` boxed Int32 개체로 값 0과 1, 각각 해결으로 초기화 됩니다. 예:  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 따라서 명시적 초기화, 할당 및 null에 대 한 추적 핸들의 비교를 수행 하기 위해 new 키워드를 사용 하 여 `nullptr`합니다.  원래 예제를 올바르게 변환 모양은 다음과 같습니다.  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 이 인해 다소 이식 하는 기존 코드를 새 구문으로 복잡 합니다. 예를 들어, 다음 값 클래스 선언을 생각해 보세요.  
  
```  
__value struct Holder {  
   Holder( Continuation* c, Sexpr* v ) {  
      cont = c;  
      value = v;  
      args = 0;  
      env = 0;  
   }  
  
private:  
   Continuation* cont;  
   Sexpr * value;  
   Environment* env;  
   Sexpr * args __gc [];  
};  
```  
  
 여기에서 둘 다 `args` 및 `env` 는 CLR 참조 형식입니다. 이러한 두 멤버를 초기화 하는 `0` 생성자에서 그대로 유지 되지 않습니다 새 구문으로 전환에서 합니다. 하도록 변경 되어야 합니다 대신 `nullptr`:  
  
```  
value struct Holder {  
   Holder( Continuation^ c, Sexpr^ v )  
   {  
      cont = c;  
      value = v;  
      args = nullptr;  
      env = nullptr;  
   }  
  
private:  
   Continuation^ cont;  
   Sexpr^ value;  
   Environment^ env;  
   array<Sexpr^>^ args;  
};  
```  
  
 마찬가지로, 이러한 멤버과 비교 하도록 테스트 `0` 멤버를 비교 하려면 변경 해야 `nullptr`합니다. Managed Extensions 구문은 다음과 같습니다.  
  
```  
Sexpr * Loop (Sexpr* input) {  
   value = 0;  
   Holder holder = Interpret(this, input, env);  
  
   while (holder.cont != 0) {  
      if (holder.env != 0) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != 0) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 다음은 새, 각 교체 `0` 인스턴스는 `nullptr`합니다. 대부분을 자동화 하 여이 변환에서 변환 도구를 통해 하지 않은 경우 모든 항목을 포함 하 여 사용 된 `NULL` 매크로입니다.  
  
```  
Sexpr ^ Loop (Sexpr^ input) {  
   value = nullptr;  
   Holder holder = Interpret(this, input, env);  
  
   while ( holder.cont != nullptr ) {  
      if ( holder.env != nullptr ) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != nullptr ) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 `nullptr` 포인터 또는 추적 핸들 형식으로 변환 되지만 정수 계열 형식으로 확장 되지 않습니다. 예를 들어 다음과 같은 초기화, 집합에에서는 `nullptr` 는 처음 두를 초기 값 으로만 사용할 합니다.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0  
int ival = nullptr;  
```  
  
 마찬가지로,는 오버 로드 된 메서드 집합을 다음과 같이 가정합니다.  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 사용한 호출은 `nullptr` 다음과 같은 리터럴  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 모호 하기 때문에 `nullptr` 추적 핸들 및 포인터를 둘 다 일치 및 다른 됩니다. (이 경우 명시적 캐스트가 필요 모호성을 제거 하려면.)  
  
 사용한 호출은 `0` 정확히 일치 하는 항목 인스턴스 (3):  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 때문에 `0` 는 정수 형식입니다. 된 `f(int)` 없음, 호출 명확 하 게 일치 `f(char*)` 표준 변환을 통해 합니다. 일치 규칙 표준 변환이 정확히 일치 하는 값의 우선 순위를 부여 합니다. 정확히 일치 없을 경우에서 표준 변환이 보다 우선을 순위가 높습니다 암시적으로 값 형식 boxing 합니다. 이 모호성이 없는 때문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 형식 (C + + /cli CL)](../dotnet/managed-types-cpp-cl.md)   
 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)   
 [개체 연산자 (^)에 대 한 핸들](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)