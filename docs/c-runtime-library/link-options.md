---
title: "링크 옵션 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0108ecd9d0b9caaa2df3d450c185d5937a96463
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="link-options"></a>링크 옵션
CRT 라이브러리 디렉터리에는 코드를 변경하지 않고도 특정 CRT 기능을 사용할 수 있는 작은 개체 파일이 여러 개 포함되어 있습니다. 이러한 파일은 링커 명령줄에 추가하기만 하면 사용할 수 있기 때문에 "링크 옵션"이라고 합니다.  
  
 순수 모드 버전은 Visual Studio 2015부터 더 이상 사용되지 않습니다. 네이티브 및 /clr 코드에는 일반 버전을 사용합니다.  
  
|네이티브 및 /clr|순수 모드|설명|  
|----------------------|---------------|-----------------|  
|binmode.obj|pbinmode.obj|기본 파일 변환 모드를 이진으로 설정합니다. [_fmode](../c-runtime-library/fmode.md)를 참조하세요.|  
|chkstk.obj|N/A|CRT를 사용하지 않는 경우 스택 검사 및 alloca를 지원합니다.|  
|commode.obj|pcommode.obj|전역 커밋 플래그를 "커밋"으로 설정합니다. [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) 및 [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)를 참조하세요.|  
|fp10.obj|N/A|기본 정밀도 컨트롤을 64비트로 변경합니다. [부동 소수점 지원](../c-runtime-library/floating-point-support.md)을 참조하세요.|  
|invalidcontinue.obj|pinvalidcontinue.obj|아무 작업도 수행하지 않는 기본 잘못된 매개 변수 처리기를 설정합니다. 즉, CRT 함수에 전달된 잘못된 매개 변수는 단순히 errno를 설정하고 오류 결과를 반환합니다.|  
|loosefpmath.obj|N/A|부동 소수점 코드에서 비정상적인 값을 허용하도록 합니다.|  
|newmode.obj|pnewmode.obj|[malloc](../c-runtime-library/reference/malloc.md)가 실패 시 새 처리기를 호출하도록 합니다. [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) 및 [realloc](../c-runtime-library/reference/realloc.md)를 참조하세요.|  
|noarg.obj|pnoarg.obj|argc 및 argv의 모든 처리를 사용하지 않도록 설정합니다.|  
|nochkclr.obj|해당 없음|아무 작업도 수행하지 않습니다. 프로젝트에서 제거합니다.|  
|noenv.obj|pnoenv.obj|CRT에 대해 캐시된 환경 만들기를 사용하지 않도록 설정합니다.|  
|nothrownew.obj|pnothrownew.obj|CRT의 throw되지 않는 새 버전을 사용하도록 설정합니다. [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하세요.|  
|setargv.obj|psetargv.obj|명령줄 인수 와일드 카드 확장을 사용하도록 설정합니다. [와일드카드 인수 확장](../c-language/expanding-wildcard-arguments.md)을 참조하세요.|  
|threadlocale.obj|pthreadlocale.obj|기본적으로 모든 새 스레드에 스레드별 로캘을 사용하도록 설정합니다.|  
|wsetargv.obj|pwsetargv.obj|명령줄 인수 와일드 카드 확장을 사용하도록 설정합니다. [와일드카드 인수 확장](../c-language/expanding-wildcard-arguments.md)을 참조하세요.|  
  
## <a name="see-also"></a>참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)