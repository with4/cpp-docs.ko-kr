---
title: "CLR 배열 선언 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array 키워드[C++]"
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CLR 배열 선언
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 관리되는 배열을 선언, 인스턴스화 및 초기화하는 구문이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions에서 CLR 배열 개체를 선언하려면 아래 예제와 같이 표준 배열 선언을 확장하여 `__gc` 키워드를 배열 개체의 이름과 쉼표로 채워진 차원 사이에 배치해야 했습니다.  
  
```  
void PrintValues( Object* myArr __gc[]);  
void PrintValues( int myArr __gc[,,]);  
```  
  
 새 구문에서는 이러한 방식이 간소화되어 STL `vector` 선언과 비슷한 템플릿 스타일의 선언을 사용합니다.  첫 번째 매개 변수는 요소 형식을 나타냅니다.  두 번째 매개 변수는 배열 차원을 지정합니다. 기본값은 1이므로 두 번째 인수는 다중 차원에만 사용하면 됩니다.  배열 개체 자체는 추적 핸들이므로 캐럿을 사용해야 합니다.  요소 형식도 참조 형식인 경우에는 요소 형식에도 캐럿을 사용해야 합니다.  예를 들어, 위 예제를 새 구문으로 표현하면 다음과 같습니다.  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
 참조 형식은 개체가 아닌 추적 핸들이므로 함수의 반환 형식으로 CLR 배열을 지정할 수 있습니다. 반면 네이티브 배열을 함수의 반환 형식으로 지정할 수는 없습니다. Managed Extensions에서 이 작업을 수행하기 위한 구문은 다소 직관적이지 못했습니다.  예를 들면 다음과 같습니다.  
  
```  
Int32 f() [];  
int GetArray() __gc[];  
```  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 훨씬 간단하게 선언할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
 관리되는 지역 배열을 간단하게 줄여서 초기화하는 방법은 두 버전의 언어에서 모두 지원됩니다.  예를 들면 다음과 같습니다.  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = {   
      __box(26), __box(27), __box(28), __box(29), __box(30)  
   };  
   return a1;  
}  
```  
  
 위 코드는 새 구문에서 훨씬 더 간단하게 줄일 수 있습니다. 새 구문에서는 boxing이 암시적이므로 `__box` 연산자가 사용되지 않습니다. 자세한 내용은 [값 형식 및 동작\(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)을 참조하십시오.  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
   return a1;  
}  
```  
  
 배열은 CLR 참조 형식이므로 각 배열 개체의 선언은 추적 핸들입니다.  따라서 배열 개체는 CLR 힙에 할당해야 합니다. 간략한 표기법에서는 관리되는 힙 할당이 숨겨집니다. 다음은 Managed Extensions에서 배열 개체를 명시적으로 초기화하는 구문입니다.  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 새 구문에서는 `new` 식이 `gcnew`로 대체되었습니다.  차원 크기는 다음과 같이 `gcnew` 식에 매개 변수로 전달됩니다.  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 새 구문에서는 `gcnew` 식 다음에 명시적 초기화 목록을 사용할 수 있지만, Managed Extensions에서는 이러한 방식이 지원되지 않습니다.  예를 들면 다음과 같습니다.  
  
```  
// explicit initialization list following gcnew   
// was not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## 참고 항목  
 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)