---
title: 국가별 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f4edcae610f17409c319c7b4bd39dc137e1211e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858704"
---
# <a name="international-enabling"></a>국가별 사용
대부분의 일반적인 C 및 c + + 코드에서는 국가별 응용 프로그램에 대 한 잘 작동 하지 않는 문자 및 문자열 조작에 대 한 가정을 합니다. 런타임 라이브러리와 MFC MBCS 또는 유니코드를 지원 하지만 사업이 있으므로 여전히 작업을 수행할 수 있습니다. 이 섹션에서는 사용자를 안내 하 Visual c + +에서 "국가별 사용"의 의미를 설명 합니다.  
  
-   유니코드와 MBCS MFC 함수 매개 변수 목록이 있는 이식 가능한 데이터 형식을 통해 사용 및 반환 형식입니다. 빌드 기호를 정의 하는 여부에 따라 적절 한 방법으로 이러한 형식은 조건부로 정의 됩니다 **_UNICODE** 또는 기호 **_MBCS** (뜻함 DBCS). MFC 라이브러리의 여러 변형이 자동 빌드 정의 따라 이러한 두 가지 기호 중 응용 프로그램으로 연결 됩니다.  
  
-   클래스 라이브러리 코드를 사용 하 여 이식 가능한 런타임 함수 및 다른 방법 유니코드 또는 MBCS에 대 한 올바른 동작을 확인 합니다.  
  
-   여전히 코드에서 특정 종류의 국가별 작업 처리 해야 합니다.  
  
    -   MFC 이식 가능한 환경 중 하나에서 구성 하는 동일한 이식 가능 런타임 함수를 사용 합니다.  
  
    -   리터럴 문자열 및 문자를 환경 중 하나에서 이식 가능 하도록 만듭니다를 사용 하는 **_T** 매크로입니다. 자세한 내용은 참조 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
    -   MBCS에서 문자열을 구문 분석할 때에 주의 해야 합니다. 이러한 예방 조치 유니코드 필요 하지 않습니다. 자세한 내용은 참조 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)합니다.  
  
    -   응용 프로그램에서 ANSI (8 비트) 및 유니코드 (16 비트) 문자를 함께 사용할 경우 주의 해야 합니다. 프로그램의 일부에서 ANSI 문자 및, 다른 유니코드 문자를 사용할 수 있지만 동일한 문자열에서 함께 사용할 수 없습니다.  
  
    -   응용 프로그램에서 문자열을 하드 코딩 하지 마십시오. 대신, 있도록 STRINGTABLE 리소스 응용 프로그램의.rc 파일을 추가 하 여 합니다. 그런 다음 소스 코드를 변경 하거나 다시 컴파일하지 않고도 응용 프로그램을 지역화할 수 있습니다. STRINGTABLE 리소스에 대 한 자세한 내용은 참조 [문자열 편집기](../windows/string-editor.md)합니다.  
  
> [!NOTE]
>  유럽 및 MBCS 문자 집합 악센트 부호 문자, 0x80 보다 큰 문자 코드와 같은 일부 문자 있어야 합니다. 0x80 보다 큰이 문자로 변환 하는 경우 부호 확장은 대부분의 코드 서명 된 문자를 사용 하므로 `int`합니다. 배열 인덱싱에 문제 처리 되어 부호 확장 문자 음수로 배열 밖에 인덱싱되므로 합니다. 예: 한국어, MBCS를 사용 하는 언어는 또한 고유 합니다. 1 개 또는 2 바이트 문자가 포함 될 수 있습니다, 때문에 동시에 두 바이트를 항상 처리 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)   
 [국제화 전략](../text/internationalization-strategies.md)