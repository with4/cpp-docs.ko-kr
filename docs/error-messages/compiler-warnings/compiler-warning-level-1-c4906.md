---
title: "컴파일러 경고 (수준 1) C4906 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4906
dev_langs: C++
helpviewer_keywords: C4906
ms.assetid: 05318e74-799b-412a-9dce-f02b8161d762
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 784bce01aa18991a28e4410f9fbaf3eb502ddd60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4906"></a>컴파일러 경고(수준 1) C4906
문자열 리터럴을 'LPWSTR'로 캐스팅했습니다.  
  
 컴파일러는 안전 하지 않은 캐스트를 발견 했습니다. 캐스트가 성공 했지만 있지만 변환 루틴을 사용 해야 합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4906 오류가 생성 됩니다.  
  
```  
// C4906.cpp  
// compile with: /W1  
#pragma warning(default : 4906)  
#include <windows.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
    LPWSTR x = (LPWSTR)"1234";   // C4906  
  
    // try the following lines instead  
    // char y[128];  
    // size_t numberOfCharConverted = 0;  
    // errcode err = 0;  
    // err = wcstombs_s(&numberOfCharConverted , &y[0], 128,  
    //                  L"12345", 4);  
    // if (err != 0)  
    // {  
    //     printf_s("wcstombs_s failed!");  
    //     return -1;  
    // }  
    // printf_s("%s\n", y);  
  
    return 0;  
}  
```