---
title: "CLR 배열 선언 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3f263227d437ddafb65ac3da0829414e4af05855
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="declaration-of-a-clr-array"></a>CLR 배열 선언
선언 구문은 인스턴스화하고 관리 되는 배열 초기화에서 변경 되었습니다 Managed Extensions for c + + Visual c + +.  
  
 Managed extensions에서 CLR 배열 개체의 선언 된는 표준 배열 선언의 확장 된 `__gc` 배열 개체의 이름 및 그 다음 쌍에서와 같이 쉼표로 채워진 차원 사이 키워드 배치 되었습니다 예제:  
  
```  
void PrintValues( Object* myArr __gc[]);  
void PrintValues( int myArr __gc[,,]);  
```  
  
 이러한 방식이 c + + 표준 라이브러리 비슷한 템플릿 선언을 사용할 수 있는 새 구문에서 간소화 되어 `vector` 선언 합니다. 첫 번째 매개 변수 요소 형식을 나타냅니다. 두 번째 매개 변수는 배열 차원 지정 (기본 값 1의 여러 차원에만 필요 두 번째 인수). Array 개체 자체는 추적 핸들 및 하므로 해야 캐럿을 사용 합니다. 요소 형식은 참조 형식 이기도 한 경우에 hat도 필요 합니다. 예를 들어 위의 예제에서는 새 구문에서 표시 될 때 모양은 다음과 같습니다.  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
 되기 때문에 참조 형식은 개체가 아니라 추적 핸들을 함수 반환 형식으로 CLR 배열을 지정할 수 있습니다. (반대로 네이티브 배열을 함수 반환 형식으로 지정할 수 있습니다.) Managed extensions에서이 작업을 수행 하는 구문은 약간 비 직관적 했습니다. 예:  
  
```  
Int32 f() [];  
int GetArray() __gc[];  
```  
  
 Visual c + +에서는 declaration은 훨씬 더 간단 합니다. 예를 들어 개체에 적용된  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
 로컬 관리 되는 배열의 줄임 초기화 언어의 두 버전에서 지원 됩니다. 예:  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = {   
      __box(26), __box(27), __box(28), __box(29), __box(30)  
   };  
   return a1;  
}  
```  
  
 새 구문 크게 간소화 됩니다 (새 구문에서 암시적 boxing 이므로 유의 `__box` 연산자가 제거 되어-참조 [값 형식 및 해당 동작 (C + + /cli CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md) 토론에 대 한):  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
   return a1;  
}  
```  
  
 배열 CLR 참조 형식을 이기 때문에 각 배열 개체의 선언에는 추적 핸들입니다. 따라서 배열 개체는 CLR 힙으로부터에 할당 해야 합니다. (관리 되는 힙 할당 줄임 표기를 숨깁니다.) 명시적 형식의 Managed extensions 배열 개체 초기화는 다음과 같습니다.  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 새 구문에서 `new` 식으로 대체 됩니다 `gcnew`합니다. 차원 크기를 매개 변수로 전달 되는 `gcnew` 다음과 같이 식:  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 새 구문에서 명시적 초기화 목록을 따를 수는 `gcnew` 식; Managed extensions에서이 지원 되지 않습니다. 예:  
  
```  
// explicit initialization list following gcnew   
// was not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 형식 (C + + /cli CL)](../dotnet/managed-types-cpp-cl.md)   
 [배열](../windows/arrays-cpp-component-extensions.md)