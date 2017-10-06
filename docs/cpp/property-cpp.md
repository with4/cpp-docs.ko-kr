---
title: "속성 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- property_cpp
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d4cb68d02f9ee543c2d3271bc48ad4318352faa2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="property-c"></a>속성 (C++)
**Microsoft 전용**  
  
 이 특성은 클래스 또는 구조체 정의에서 비정적 "가상 데이터 멤버"에 적용할 수 있습니다. 컴파일러는 해당 참조를 함수 호출로 변경하여 이러한 "가상 데이터 멤버"를 데이터 멤버로 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## <a name="remarks"></a>설명  
 컴파일러가 멤버 선택 연산자의 오른쪽에이 특성으로 선언 된 데이터 멤버를 확인 하는 경우 ("**.**"또는"**->**"), 작업을 변환는 **가져오기** 또는 **배치** 이러한 식은 l-value 또는 r-value 인지에 따라 함수입니다. 보다 복잡 한 컨텍스트에서와 같은 "`+=`", 다시 작성 둘 다 수행 하 여 수행 됩니다 **가져오기** 및 **배치**합니다.  
  
 이 특성은 클래스 또는 구조체 정의에 있는 빈 배열의 선언에서도 사용할 수 있습니다. 예:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 위의 문은 `x[]`를 하나 이상의 배열 인덱스와 함께 사용할 수 있음을 나타냅니다. 이 경우 `i=p->x[a][b]`가 `i=p->GetX(a, b)`로 바뀌고 `p->x[a][b] = i`가 `p->PutX(a, b, i);`로 바뀝니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)
