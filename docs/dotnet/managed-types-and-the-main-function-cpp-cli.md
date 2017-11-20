---
title: "관리 되는 형식 및 main 함수 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- main function, in managed applications
- managed code, main() function
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1a6d8b330108c5fba953567493551894036a7a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="managed-types-and-the-main-function-ccli"></a>관리되는 형식 및 main 함수(C++/CLI)
사용 하 여 응용 프로그램을 작성할 때 **/clr**의 인수는 **main ()** 함수는 관리 되는 형식일 수 없습니다.  
  
 적절 한 서명의 예는.  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 형식(C++/CLI)](../dotnet/managed-types-cpp-cli.md)