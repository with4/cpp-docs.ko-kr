---
title: "방법: 같음 여부 테스트 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: equality, testing for
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cbaddee30c9b02b99c10852b7e9c0d425d80ebb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-test-for-equality-ccli"></a>방법: 같음 여부 테스트(C++/CLI)
다음 샘플에서는 c + +에 대 한 관리 되는 확장을 사용 하 여 같음 테스트를 기반으로를 핸들 참조 합니다.  
  
## <a name="example"></a>예제  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 이 프로그램에 대 한 IL op_Equality에 대 한 호출을 사용 하 여 반환 값을 구현 하는 것을 표시 합니다.  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 형식(C++/CLI)](../dotnet/managed-types-cpp-cli.md)