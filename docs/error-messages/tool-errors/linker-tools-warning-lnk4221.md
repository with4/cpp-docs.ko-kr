---
title: "링커 도구 경고 LNK4221 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4221
dev_langs: C++
helpviewer_keywords: LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3fb348ebb05b7af40821b4f3968a920c2e9e773
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4221"></a>링커 도구 경고 LNK4221
이 개체 파일 하므로이 라이브러리를 사용 하는 모든 링크 작업에서 사용 되지 않습니다.는 이전에 정의 되지 않은 공용 기호를 정의 하지 않습니다.  
  
 다음 두 가지 코드 조각을 고려해 야 합니다.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 실행 파일을 컴파일하고 두 개의 개체 파일 만들기를 **cl /c a.cpp b.cpp** 명령 프롬프트입니다. 개체 파일을 실행 하 여 연결 되는 경우 **/out:test.lib a.obj b.obj /lib 연결**, LNK4221 경고를 받게 됩니다. 실행 하 여 개체를 연결 하는 경우 **/out:test.lib b.obj a.obj /lib 연결**, 경고가 표시 되지 것입니다.  
  
 경고가 발생 하지 않습니다는 두 번째 시나리오에서 링커는 방식으로 lifo (후입선출) 방식으로 작동 하기 때문에 있습니다. 첫 번째 시나리오에서는 b.obj a.obj, 보다 먼저 처리 됩니다 되었으며 a.obj 추가할 새 기호가 없습니다. A.obj를 먼저 처리 하도록 링커에 지시를 하 여 경고를 방지할 수 있습니다.  
  
 이 오류의 일반적인 원인에는 두 개의 소스 파일 옵션을 지정 하는 경우 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 에 지정 된 헤더 파일 이름으로는 **미리 컴파일된 헤더** 필드입니다. 이 문제의 일반적인 원인은 다룹니다 stdafx.h 있으므로 기본적으로 stdafx.cpp stdafx.h를 포함 하 고 새 기호를 추가 하지 않습니다. 다른 소스 파일 stdafx.h와 포함 하는 경우 **/Yc** stdafx.obj 하기 전에 연결 된.obj 파일을 처리를 링커 LNK4221 throw 됩니다.  
  
 한 가지 방법은 고유 하도록 각 미리 컴파일된 헤더에 대해이 문제를 해결할 수, 있기 사용 하 여 포함 된 하나의 소스 파일이 **/Yc**합니다. 다른 모든 소스 파일에는 미리 컴파일된 헤더 사용 해야 합니다. 이 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)합니다.