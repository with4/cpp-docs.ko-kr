---
title: 로캘 및 코드 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], about locales
- locale IDs [C++]
- locales [C++]
- code pages [C++]
- code pages [C++], dynamically changing
- character sets [C++], code pages
- multibyte code pages [C++]
- character sets [C++], locales
- localization [C++], code pages
- localization [C++], locales
- code pages [C++], locales
- conventions [C++], international character support
ms.assetid: bd937361-b6d3-4c98-af95-beb7c903187b
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7dd3c5356df7b80f21605e325158e87cc5a71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858148"
---
# <a name="locales-and-code-pages"></a>로캘 및 코드 페이지
로캘 ID는 로컬 규칙과 특정 지리적 지역에 대 한 언어를 반영합니다. 지정된 언어는 여러 국가/지역에서 통용될 수 있습니다. 예를 들어 포르투갈어는 브라질과 포르투갈에서 통용됩니다. 반대로 한 국가/지역에 여러 개의 공식 언어가 있을 수 있습니다. 예를 들어, 캐나다에서는 두 언어: 영어와 프랑스어 합니다. 따라서 캐나다에 두 가지 로캘이: 캐나다 영어와 프랑스어 (캐나다). 일부 로캘 종속 범주에는 날짜 형식 지정 및 통화 값의 형식 표시가 포함됩니다.  
  
 언어에 따라 텍스트 및 데이터 형식 지정 규칙이 결정되고 국가/지역에 따라 지역 규칙이 결정됩니다. 모든 언어에는 고유한 매핑을 코드 페이지가 나타내는 (예: 문장 부호 및 숫자) 알파벳에서 이외의 문자를 포함 하는 합니다. 코드 페이지 문자 집합 및 언어 관련 됩니다. 따라서 한 [로캘](../c-runtime-library/locale.md) 은 언어, 국가/지역 및 코드 페이지의 고유한 조합입니다. 호출 하 여 로캘 및 코드 페이지 설정이 런타임 시 변경할 수 있습니다는 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 함수입니다.  
  
 언어 마다 다른 코드 페이지를 사용할 수 있습니다. 예를 들어 ANSI 코드 페이지 1252는 영어와 대부분의 유럽 언어에 대 한 사용 및 ANSI 코드 페이지 932는 일본어 간지에 사용 됩니다. 실제로 모든 코드 페이지는 ASCII 문자는 가장 낮은 128 자 (0x00-0x7F)에 대 한 집합을 공유 합니다.  
  
 모든 단일 바이트 코드 페이지 (256 항목)이 있는 테이블 (숫자 및 문장 부호 포함), 문자 또는 문자 모양에 바이트 값의 매핑은으로 나타낼 수 있습니다. 더블 바이트 문자 값의 (64k 엔트리가) 매우 큰 테이블으로 모든 멀티 바이트 코드 페이지를 나타낼 수도 있습니다. 그러나 실제이 페이지는 일반적으로 평균 (싱글바이트) 문자에 대 한 테이블 더블 바이트 값에 대 한 범위로 표현 됩니다.  
  
 코드 페이지에 대한 자세한 내용은 [Code Pages](../c-runtime-library/code-pages.md)를 참조하세요.  
  
 C 런타임 라이브러리에 두 가지 유형의 내부 코드 페이지: 로캘 및 멀티 바이트입니다. 프로그램 실행 중 현재 코드 페이지를 변경할 수 있습니다 (에 대 한 설명서를 참조는 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 및 [_setmbcp](../c-runtime-library/reference/setmbcp.md) 함수). 또한 런타임 라이브러리 가져와서는 프로그램의 실행 기간에 대 한 상수는 운영 체제 코드 페이지의 값을 사용할 수 있습니다.  
  
 로캘 코드 페이지 변경 되는 경우 선택한 코드 페이지에 적용 하는 변경 내용 함수는 로캘 종속 집합의 동작입니다. 기본적으로 모든 로캘 종속 기능 "C" 로캘에서에 고유한 로캘 코드 페이지를 사용 하 여 실행을 시작합니다. 내부 로캘 코드 페이지 (뿐만 아니라 다른 로캘 관련 속성)를 호출 하 여 변경할 수 있습니다는 `setlocale` 함수입니다. 에 대 한 호출 `setlocale`(LC_ALL, "") 운영 체제 사용자 로캘으로 표시 되는 로캘을 설정 합니다.  
  
 마찬가지로, 멀티 바이트 코드 페이지 변경 되는 경우의 지시 선택한 코드 페이지에 따라 멀티 바이트 함수의 변경 동작입니다. 기본적으로 모든 멀티 바이트 함수는 멀티 바이트 코드 페이지에 해당 하는 운영 체제의 기본 코드 페이지와 실행을 시작 합니다. 호출 하 여 내부 멀티 바이트 코드 페이지를 변경할 수는 `_setmbcp` 함수입니다.  
  
 C 런타임 함수 `setlocale` 설정, 변경 또는 현재 프로그램의 로캘 정보의 일부나 전부를 쿼리 합니다. [_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 루틴의 와이드 문자 버전은 `setlocale`; 인수 및 반환 값의 `_wsetlocale` 는 와이드 문자 문자열입니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)   
 [문자 집합 이식성의 이점](../text/benefits-of-character-set-portability.md)