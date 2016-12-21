---
title: "속성 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "property_cpp"
  - "Property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], 속성"
  - "property __declspec 키워드"
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 속성 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이 특성은 클래스 또는 구조체 정의에서 비정적 "가상 데이터 멤버"에 적용할 수 있습니다.  컴파일러는 해당 참조를 함수 호출로 변경하여 이러한 "가상 데이터 멤버"를 데이터 멤버로 처리합니다.  
  
## 구문  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## 설명  
 컴파일러가 멤버 선택 연산자\("**.**" 또는 "**\-\>**"\)의 오른쪽에서 이 특성을 사용하여 선언된 데이터 멤버를 확인하면 해당 식이 I\-value인지 아니면 r\-value인지에 따라 **get** 또는 **put** 함수로 연산을 변환합니다.  "`+=`"와 같은 보다 복잡한 컨텍스트에서는 **get** 및 **put**을 둘 다 수행하여 다시 작성됩니다.  
  
 이 특성은 클래스 또는 구조체 정의에 있는 빈 배열의 선언에서도 사용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 위의 문은 `x[]`를 하나 이상의 배열 인덱스와 함께 사용할 수 있음을 나타냅니다.  이 경우 `i=p->x[a][b]`가 `i=p->GetX(a, b)`로 바뀌고 `p->x[a][b] = i`가 `p->PutX(a, b, i);`로 바뀝니다.  
  
 **Microsoft 전용 종료**  
  
## 예제  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)