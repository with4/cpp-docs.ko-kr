---
title: -스택 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82111ce950d14bc6b3e270ee9a658d806b28b62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션 스택 크기를 바이트 단위로 설정 하 고 10 진수 또는 C 언어 표기법 인수를 사용 합니다. /STACK 옵션 실행 파일에만 적용 됩니다.  
  
 *예약* 인수 가상 메모리의 총 스택 할당을 지정 합니다. EDITBIN 가장 가까운 4 바이트에 지정된 된 값으로 반올림합니다.  
  
 선택적 `commit` 인수는 운영 체제에서 해석 합니다. Windows NT, Windows 95 및 Windows 98에서 `commit` 한 번에 할당할 실제 메모리 양을 지정 합니다. 커밋된 가상 메모리 공간을 예약 하는 페이징 파일에서 발생 합니다. 더 높은 `commit` 값 시간 때 응용 프로그램이 더 많은 스택 공간이 필요할 수 있지만 늘어나고의 메모리 요구 사항을 시작 시간을 절약할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)