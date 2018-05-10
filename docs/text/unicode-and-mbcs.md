---
title: 유니코드 및 MBCS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], Unicode
- MFC [C++], character sets
- character sets [C++], multibyte
- run-time libraries [C++], language portability
- character sets [C++], Unicode
- Unicode [C++], MFC and C run-time functions
- multibyte characters [C++]
- runtime [C++], language portability
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e10c07e11cbe940b5f7cfee460ddd33f6f5ff1f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="unicode-and-mbcs"></a>유니코드 및 MBCS
Microsoft Foundation 클래스 (MFC) 라이브러리, Visual c + +에 대 한 C 런타임 라이브러리 및 Visual c + + 개발 환경 국제 프로그래밍을 지원 하기 위해 활성화 됩니다. 제공:  
  
-   Windows에서 유니코드 표준 지원 합니다. 유니코드는 현재의 표준이며 어디에서든 항상 사용 가능해야 합니다.  
  
     유니코드는는 16 비트 문자 인코딩, 모든 언어에 대 한 충분 한 인코딩을 제공 합니다. 모든 ASCII 문자는 유니코드에서 와이드 문자로 서 포함 됩니다.  
  
-   모든 플랫폼에서 더블 바이트 문자 집합 (DBCS) 불리 멀티 바이트 문자 집합 (MBCS)의 형태를 지원 합니다.  
  
     DBCS 문자는 1 개 또는 2 바이트로 구성 합니다. 바이트의 범위는 선행 바이트로 사용 하기 위해 따로 설정 됩니다. 선행 바이트는 자신과 다음 후행 바이트가 단일 2 바이트 문자를 구성 하도록 지정 합니다. 하면 해야는 추적 하는 바이트는 선행 바이트. 특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 특정 범위 내에 속합니다. 이러한 범위가 겹치는 경우 상황에 지정 된 바이트가 선행 바이트 또는 후행 바이트로 작동 하는지 확인 해야 할 수도 있습니다.  
  
-   국제 시장을 겨냥 한 작성 된 응용 프로그램의 MBCS 프로그래밍을 단순화 하는 도구를 지원 합니다.  
  
     MBCS 지원 버전의 Windows 운영 체제, Visual c + + 개발 시스템에서 실행할 때-통합된 소스 코드 편집기, 디버거 및 명령줄 도구를 포함 하 여-는 완전히 MBCS를 지원 합니다. 자세한 내용은 참조 [Visual c + +에서 MBCS 지원](../text/mbcs-support-in-visual-cpp.md)합니다.  
  
> [!NOTE]
>  이 설명서에서는 MBCS 멀티 바이트 문자에 대 한 모든 유니코드가 아닌 지원을 설명 하는 데 사용 됩니다. Visual c + +에서 MBCS 항상 DBCS를 의미합니다. 2 바이트는 지원 되지 않습니다 보다 큰 문자 집합.  
  
 정의 ASCII 문자 집합에는 모든 멀티 바이트 문자 집합의 일부입니다. 많은 멀티바이트 문자 집합에서 0x00 - 0x7F 범위의 각 문자는 ASCII 문자 집합에 동일한 값을 가진 문자와 같습니다. 예를 들어, ASCII와 MBCS 문자열, 1 바이트에서에서 **NULL** 문자 ('\0') 값 0x00 고 null 종결 문자를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [국가별 사용](../text/international-enabling.md)