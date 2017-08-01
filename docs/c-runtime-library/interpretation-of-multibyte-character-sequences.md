---
title: "멀티바이트 문자 시퀀스 해석 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.character.multibyte
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8b8cd1cc92d422f876b67a66bb5d28dd8ba1843b
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="interpretation-of-multibyte-character-sequences"></a>멀티바이트 문자 시퀀스 해석
Microsoft 런타임 라이브러리에 있는 대부분의 멀티바이트 문자 루틴이 멀티바이트 코드 페이지와 관련된 멀티바이트 문자 시퀀스를 인식합니다. 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  
  
### <a name="locale-dependent-multibyte-routines"></a>로캘 종속 멀티바이트 루틴  
  
|루틴|기능|  
|-------------|---------|  
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|멀티바이트 문자의 바이트 수의 유효성을 검사하고 해당 수를 반환합니다.|  
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|멀티바이트 문자열: 문자열에 있는 각 문자의 유효성을 검사하고 문자열 길이를 반환합니다. 와이드 문자열: 문자열 길이를 반환합니다.|  
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|멀티바이트 문자의 시퀀스를 해당되는 와이드 문자 시퀀스로 변환합니다.|  
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|멀티바이트 문자를 해당되는 와이드 문자로 변환합니다.|  
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|와이드 문자의 시퀀스를 해당되는 멀티바이트 문자의 시퀀스로 변환합니다.|  
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|와이드 문자를 해당되는 멀티바이트 문자로 변환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
