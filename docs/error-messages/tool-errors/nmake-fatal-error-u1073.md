---
title: NMAKE 심각한 오류 U1073 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dde9ca2f4a15edf6599dcc31b39d9411645f2a6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316308"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE 심각한 오류 U1073
'targetname'를 확인 하는 방법을 알 수 없습니다  
  
 지정된 된 대상 없고 명령이 실행 또는 유추 규칙을 적용할 수 없습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  대상 이름 철자를 확인 합니다.  
  
2.  경우 *targetname* 는 의사는 다른 설명 블록에 대상으로 지정 합니다.  
  
3.  경우 *targetname* 는 매크로 호출 null 문자열로 확장 되지 않고 해야 합니다.