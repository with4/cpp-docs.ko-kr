---
title: "NMAKE 심각한 오류 U1073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faae317df44560991a88d47ec7f123e6a8126429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE 심각한 오류 U1073
'targetname'를 확인 하는 방법을 알 수 없습니다  
  
 지정된 된 대상 없고 명령이 실행 또는 유추 규칙을 적용할 수 없습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  대상 이름 철자를 확인 합니다.  
  
2.  경우 *targetname* 는 의사는 다른 설명 블록에 대상으로 지정 합니다.  
  
3.  경우 *targetname* 는 매크로 호출 null 문자열로 확장 되지 않고 해야 합니다.