---
title: "컴파일러 경고 (수준 1) C4627 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66d199b8dede21f94a963113341eb6426f66a807
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4627"></a>컴파일러 경고(수준 1) C4627
'\<식별자 >': 미리 컴파일된 헤더 사용을 찾을 때 건너뛰었습니다  
  
 컴파일러는 미리 컴파일된 헤더 사용 되는 위치에 대 한 검색 하는 동안 발생 한 `#include` 지시문에 대 한는  *\<식별자 >* 파일을 포함 합니다. 컴파일러에서 무시는 `#include` 지시문, 경고를 실행 하지만 **C4627** 미리 컴파일된 헤더 포함 되어 있지 않은 경우는  *\<식별자 >* 파일을 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)