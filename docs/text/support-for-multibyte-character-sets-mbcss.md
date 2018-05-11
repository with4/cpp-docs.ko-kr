---
title: 멀티 바이트 문자 집합 (Mbcs)에 대 한 지원 | Microsoft Docs
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
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7b0381b570cbf9e900d44ac075876e63b6be14a8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>MBCS(멀티바이트 문자 집합) 지원
MBCS(멀티바이트 문자 집합)는 일본어 및 중국어와 같이 싱글바이트로 표현할 수 없는 문자 집합을 지원하기 위한 이전의 접근 방식입니다. 새 개발을 수행하는 경우 최종 사용자에게 표시되지 않는 시스템 문자열을 제외한 모든 텍스트 문자열에 유니코드를 사용해야 합니다. MBCS는 이전 기술이며 새로운 개발에는 사용하지 않는 것이 좋습니다.  
  
 가장 일반적인 MBCS 구현은 DBCS(더블바이트 문자 집합)입니다. DBCS에 대해 일반적으로 Visual C++ 및 특별히 MFC가 완전히 사용하도록 설정됩니다.  
  
 샘플에 대해서는 MFC 소스 코드 파일을 참조하세요.  
  
 언어에 큰 문자 집합이 사용되는 지역/국가에서 사용되는 플랫폼의 경우 유니코드 대신 MBCS를 사용하는 것이 가장 좋습니다. MFC에서는 국제화 가능한 데이터 형식 및 C 런타임 함수를 사용하여 MBCS를 지원합니다. 코드에서 같은 작업을 수행해야 합니다.  
  
 MBCS에서 문자는 1 또는 2바이트로 인코딩됩니다. 2바이트 문자에서 첫 번째 또는 선행 바이트는 해당 바이트 및 후행 바이트가 한 문자로 해석되도록 신호를 보냅니다. 첫 번째 바이트는 선행 바이트로 사용하도록 예약된 코드 범위에서 가져옵니다. 선행 바이트가 될 수 있는 바이트 범위는 사용 중인 코드 페이지에 따라 다릅니다. 예를 들어 일본어 코드 페이지 932에는 0x81~0x9F 범위가 선행 바이트로 사용되지만, 한국어 코드 페이지 949에는 다른 범위가 사용됩니다.  
  
 MBCS 프로그래밍에서는 다음을 모두 고려하세요.  
  
 환경의 MBCS 문자  
 MBCS 문자는 파일 및 디렉터리 이름과 같은 문자열에 나타날 수 있습니다.  
  
 편집 작업  
 MBCS 응용 프로그램의 편집 작업은 바이트가 아니라 문자 단위로 수행되어야 합니다. 캐럿은 한 문자를 분할하면 안 되고, 오른쪽 화살표 키는 한 문자 오른쪽으로 이동해야 합니다. **삭제** ; 문자를 삭제 해야 **실행 취소** 다시 삽입 해야 합니다.  
  
 문자열 처리  
 MBCS를 사용하는 응용 프로그램에서 문자열 처리 시 특수한 문제가 발생합니다. 두 너비의 문자는 단일 문자열로 결합되므로 선행 바이트를 확인해야 합니다.  
  
 런타임 라이브러리 지원  
 C 런타임 라이브러리 및 MFC는 단일 바이트, MBCS 및 유니코드 프로그래밍을 지원합니다. 단일 바이트 문자열은와 처리는 `str` MBCS 문자열 런타임에 함수 패밀리를 해당 처리 `_mbs` 함수 및 유니코드 문자열에 해당 하는 게 처리 됩니다 *wcs* 함수입니다. "MBCS/유니코드 이식성"의 설명대로 MFC 클래스 멤버 함수 구현에는 적합한 환경에서 함수의 일반 `str` 패밀리, MBCS 함수 또는 유니코드 함수에 매핑되는 이식 가능한 런타임 함수가 사용됩니다.  
  
 MBCS/유니코드 이식성  
 Tchar.h 헤더 파일을 사용하여 같은 소스에서 단일 바이트, MBCS 및 유니코드 응용 프로그램을 빌드할 수 있습니다. Tchar.h 접두사로 추가 하는 매크로 정의 *_tcs* , 여러 `str`, `_mbs`, 또는 *wcs* 함수 적절 하 게 합니다. MBCS를 빌드하려면 기호를 정의 **_MBCS**합니다. 유니코드를 빌드하려면 기호를 정의 **_UNICODE**합니다. 기본적으로 **_MBCS** MFC 응용 프로그램에 대해 정의 됩니다. 자세한 내용은 참조 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
> [!NOTE]
>  둘 다 정의할 경우 동작이 정의 되지 않습니다 **_UNICODE** 및 **_MBCS**합니다.  
  
 Mbctype.h 및 Mbstring.h 헤더 파일에서는 특정 경우에 필요할 수 있는 MBCS 특정 함수 및 매크로를 정의합니다. 예를 들어 `_ismbblead`는 문자열의 특정 바이트가 선행 바이트인지를 알립니다.  
  
 국가별 이식성을 위해 사용 하 여 프로그램을 코딩 [유니코드](../text/support-for-unicode.md) 또는 멀티 바이트 문자 집합 (Mbcs).  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [프로그램에서 MBCS 사용](../text/international-enabling.md)  
  
-   [유니코드와 MBCS 프로그램에서 사용](../text/internationalization-strategies.md)  
  
-   [MBCS를 사용 하 여 국제화 된 프로그램 만들기](../text/mbcs-programming-tips.md)  
  
-   [MBCS 프로그래밍 요약 참조](../text/mbcs-programming-tips.md)  
  
-   [바이트 너비 이식성에 대 한 제네릭 텍스트 매핑에 대 한 자세한 내용은](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [Visual C++에서 MBCS 지원](../text/mbcs-support-in-visual-cpp.md)