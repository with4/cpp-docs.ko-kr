---
title: 관리 되는 형식 및 main 함수 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- main function, in managed applications
- managed code, main() function
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6024f4b6e72fa997f816f7fee0b76778c5ebfc4f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131308"
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