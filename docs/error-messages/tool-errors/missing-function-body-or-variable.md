---
title: "함수 본문 또는 변수 누락 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: c80a5626e7f674ddca7d44e94aa8ab64c735c81e
ms.lasthandoff: 04/24/2017

---
# <a name="missing-function-body-or-variable"></a>함수 본문 또는 변수 누락
함수 프로토타입 컴파일러 오류 없이 계속할 수 있지만 함수 코드 또는 예약 된 변수 공간이 없을 링커가 주소에 대 한 호출을 확인할 수 없습니다. 링커에서 확인 해야 하는 함수에 대 한 호출을 만들 때까지이 오류가 나타나지 않습니다.  
  
## <a name="example"></a>예제  
 Main에서 함수 호출 프로토타입 함수가 존재 하는 컴파일러를 허용 하기 때문에 l n k 2019 발생 합니다.  링커를 찾지 못합니다.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>예제  
 C + + 클래스 정의에 클래스 및 프로토타입 뿐 아니라 특정 함수의 구현이 포함 하는 있는지 확인 합니다. 헤더 파일 외의 다른 클래스를 정의 하는 경우 포함 되어야 함수 클래스 이름 다음에 (`Classname::memberfunction`).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
