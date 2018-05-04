---
title: 예약어 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abe67e1804d436dbd44257f6d7670a71b7f74889
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="reserved-words"></a>예약어
링커에 의해에서는 다음 단어가 예약 되어 있습니다. 이러한 이름은에서 인수로 사용할 수 있습니다 [모듈 정의 문의](../../build/reference/module-definition-dot-def-files.md) 이름을 큰따옴표로 묶어야 하는 경우에 ("").  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**미리 로드**|  
|**자료**|**IOPL**|**개인**|  
|**코드**|**라이브러리**1|**PROTMODE**2|  
|**준수**|**LOADONCALL**1|**순수**1|  
|**데이터**|**LONGNAMES**2|**읽기 전용**|  
|**설명**|**이동 가능한**1|**READWRITE**|  
|**DEV386**|**이동 가능한**1|**REALMODE**1|  
|**삭제 가능한**|**여러**|**상주**|  
|**동적**|**이름**|**RESIDENTNAME**1|  
|**실행 전용**|**NEWFILES**2|**섹션**|  
|**EXECUTEONLY**|**NODATA**1|**세그먼트**|  
|**실행 읽기**|**NOIOPL**1|**공유**|  
|**EXETYPE**|**NONAME**|**단일**|  
|**EXPORTS**|**일치 하지 않는**1|**STACKSIZE**|  
|**고정**1|**NONDISCARDABLE**|**STUB**|  
|**함수**2|**없음**|**버전**|  
|**HEAPSIZE**|**비공유**|**WINDOWAPI**|  
|**가져오기**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**비**1|**개체**|**WINDOWS**|  
|**포함**2|**이전**1||  
  
 1이 용어 하면 링커에서 경고가 ("무시"). 그러나 단어는 계속 예약 되어 있습니다.  
  
 2 링커가이 단어는 무시 되지만 경고 메시지를 내보냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)