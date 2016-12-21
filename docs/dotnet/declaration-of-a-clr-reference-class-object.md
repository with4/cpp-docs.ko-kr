---
title: "CLR 참조 클래스 개체 선언 | Microsoft Docs"
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
helpviewer_keywords: 
  - "참조 형식, CLR"
  - "형식[C++], 참조 형식"
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLR 참조 클래스 개체 선언
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 참조 클래스 형식의 개체를 선언하고 인스턴스화하는 구문이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions에서 참조 클래스 형식 개체는 ISO\-C\+\+ 포인터 구문을 사용하여 선언합니다. 별표\(`*`\)의 왼쪽에 선택적 키워드인 `__gc`를 사용할 수도 있습니다.  예를 들어, Managed Extensions 구문에서 사용되는 여러 가지 참조 클래스 형식 개체 선언은 다음과 같습니다.  
  
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
  
 새 구문에서 참조 클래스 형식 개체는 새 선언 토큰\(`^`\)을 사용하여 선언합니다. 이 토큰의 공식 명칭은 *추적 핸들*이고 비공식적으로는 *모자*라고도 합니다. 추적이라는 표현은 참조 형식이 CLR 힙에 상주하며 가비지 수집으로 인한 힙 압축 과정에서 위치가 명시적으로 이동할 수 있음을 의미합니다.  추적 핸들은 런타임에 자동으로 업데이트됩니다.  비슷한 두 가지 개념인 *추적 참조*\(`%`\)와 *내부 포인터*\(`interior_ptr<>`\)에 대한 자세한 내용은 [값 형식 의미](../dotnet/value-type-semantics.md)를 참조하십시오.  
  
 ISO\-C\+\+ 포인터 구문을 다시 사용하면서 선언 구문이 제외된 주된 이유는 다음과 같습니다.  
  
-   포인터 구문을 사용하면 오버로드된 연산자를 참조 개체에 직접 적용할 수 없습니다.  프로그래머는 `rV1+rV2`와 같은 직관적인 방법을 사용하는 대신 `rV1->op_Addition(rV2)` 등의 해당 내부 이름을 사용하여 연산자를 호출해야 합니다.  
  
-   가비지 수집되는 힙에 저장된 개체에는 캐스팅 및 포인터 산술 연산 등의 몇 가지 포인터 연산을 사용할 수 없습니다.  추적 핸들이라는 개념은 CLR 참조 형식의 특성을 보다 잘 반영합니다.  
  
 추적 핸들에 `__gc` 한정자를 사용할 필요가 없으며 이러한 방식은 지원되지도 않습니다.  개체 자체의 사용 방식은 변경되지 않았습니다. 개체는 여전히 포인터 멤버 선택 연산자\(`->`\)를 통해 멤버에 액세스합니다.  예를 들어 위의 Managed Extensions 코드 예제를 새 구문으로 변환하면 다음과 같습니다.  
  
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
  
## CLR 힙에서 동적으로 개체 할당  
 Managed Extensions의 경우 네이티브 힙과 관리되는 힙 사이에 두 개의 `new` 식을 할당하는 작업은 거의 자동으로 수행되었습니다.  대부분의 경우 컴파일러에서는 메모리를 네이티브 힙에 할당할지 또는 관리되는 힙에 할당할지를 상황에 따라 판단할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 상황에 따라 힙을 할당하지 않으려면 `__gc` 또는 `__nogc` 키워드를 사용하여 컴파일러에 지시할 수 있습니다.  새 구문에서는 `gcnew` 키워드를 도입함으로써 두 new 식의 개별 특성이 명확하게 드러납니다.  예를 들어 위의 세 가지 선언은 새 구문에서 다음과 같습니다.  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 다음은 이전 단원에서 선언한 `Form1` 멤버를 Managed Extensions에서 초기화하는 예제입니다.  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 동일한 초기화를 새 구문으로 변환하면 다음과 같습니다.  `gcnew` 식의 대상인 경우 참조 형식에 대해 캐럿이 필요하지 않습니다.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## 어떠한 개체도 가리키지 않는 추적 참조  
 새 구문에서는 `0`이 더 이상 null 주소를 나타내지 않으며 `1`, `10` 또는 `100`과 같은 정수로 취급됩니다.  새로운 특수 토큰이 추적 참조의 null 값을 나타냅니다.  예를 들어, Managed Extensions에서는 다음과 같이 어떠한 개체도 가리키지 않는 참조 형식을 초기화합니다.  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 새 구문에서는 `Object`에 값 형식을 할당하거나 값 형식을 사용하여 이를 초기화하면 해당 값 형식이 암시적으로 boxing됩니다.  새 구문에서는 `obj`와 `obj2`가 모두 주소가 지정된 boxed Int32 개체로 초기화됩니다. 이 개체에는 각각 0과 1 값이 들어 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 따라서 추적 핸들을 null로 명시적으로 초기화, 할당 및 비교하려면 새 키워드인 `nullptr`를 사용해야 합니다.  원래 예제를 올바르게 수정한 결과는 다음과 같습니다.  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 그 결과, 기존 코드를 새 구문으로 이식하는 작업이 다소 복잡할 수 있습니다.  예를 들어, 다음과 같은 값 클래스 선언을 생각해 볼 수 있습니다.  
  
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
  
 여기에서 `args` 및 `env`는 모두 CLR 참조 형식입니다.  생성자에서 이러한 두 멤버를 `0`으로 초기화하는 과정은 새 구문으로 변환할 때 그대로 유지되지 않습니다.  이는 `nullptr`로 변경해야 합니다.  
  
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
  
 마찬가지로, 이러한 멤버를 `0`과 비교하는 테스트도 멤버를 `nullptr`와 비교하도록 변경해야 합니다.  다음은 Managed Extensions 구문입니다.  
  
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
  
 다음은 `0`을 모두 `nullptr`로 바꾸어 수정한 코드입니다.  변환 도구를 사용하면 전부는 아니더라도 대부분의 항목을 자동으로 변환할 수 있습니다. 여기에는 `NULL` 매크로를 사용하는 경우도 포함됩니다.  
  
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
  
 `nullptr`는 임의의 포인터 또는 추적 핸들 형식으로 변환되지만 정수 계열 형식으로 확장되지는 않습니다.  예를 들어, 다음과 같은 초기화 집합에서 `nullptr`는 처음 두 경우에 초기 값으로만 사용할 수 있습니다.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0 …  
int ival = nullptr;  
```  
  
 마찬가지로 다음과 같은 오버로드된 메서드 집합이 있다고 가정할 경우,  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 다음과 같이 `nullptr` 리터럴을 사용한 호출은  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 모호한 호출이 됩니다. 이는 `nullptr`가 추적 핸들 및 포인터와 모두 일치하며 형식 간에 우선 순위가 없기 때문입니다. 이러한 경우 모호성을 해결하려면 명시적 캐스트가 필요합니다.  
  
 `0`을 사용한 호출은 인스턴스 \(3\)과 정확하게 일치합니다.  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 이는 `0`이 정수 형식이기 때문입니다.  `f(int)`가 없다면 이 호출은 표준 변환을 통해 `f(char*)`와 모호하게 일치하게 됩니다.  일치 규칙에 따라 정확한 일치는 표준 변환보다 우선 순위가 높습니다.  정확한 일치 항목이 없는 경우 표준 변환은 값 형식에 대한 암시적 boxing보다 우선 순위가 높습니다.  따라서 이 경우에는 모호성이 없습니다.  
  
## 참고 항목  
 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [개체 연산자에 대한 핸들\(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)