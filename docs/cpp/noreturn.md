---
title: noreturn | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noreturn_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15df38143ded836b671fdfa17a7c5790a9fe960a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Microsoft 전용  
 이 `__declspec` 특성은 함수가 반환되지 않음을 컴파일러에 알립니다. 결과적으로 컴파일러 한다는 사실을 알고 있으면를 호출한 다음 코드는 **__declspec (noreturn)** 함수에 연결할 수 없습니다.  
  
 컴파일러가 값을 반환하지 않는 제어 경로를 가진 함수를 발견할 경우 경고(C4715) 또는 오류 메시지(C2202)가 생성됩니다. 반환 되지 않는 함수로 인해 제어 경로 연결할 수, 하는 경우 사용할 수 있습니다 **__declspec (noreturn)** 이 경고 또는 오류를 방지할 수 있습니다.  
  
> [!NOTE]
>  추가 **__declspec (noreturn)** 반환 하는 함수에 정의 되지 않은 동작이 발생할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 샘플에는 **다른** 절 return 문을 포함 하지 않습니다.  선언 `fatal` 으로 **__declspec (noreturn)** 오류 또는 경고 메시지를 방지 합니다.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)