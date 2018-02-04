---
title: "-volatile (volatile 키워드 해석) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
dev_langs:
- C++
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4528d53da01ae83f179f07ba52b2c86c335e883c
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile(volatile 키워드 해석)

지정 방법을 [휘발성](../../cpp/volatile-cpp.md) 해석 해야 하는 키워드입니다.

## <a name="syntax"></a>구문

> **/volatile:**{**iso**|**ms**}  

## <a name="arguments"></a>인수

**/volatile:iso**  
엄격한 선택 `volatile` ISO 표준 c + + 언어에서 정의 된 대로 의미 합니다. 의미 체계를 획득 해제 volatile 액세스에서 보장 되지 않습니다. 기본 해석 컴파일러 ARM를 대상으로 하는 경우 이것이 `volatile`합니다.

**/volatile:ms**  
선택 하는 Microsoft 확장 `volatile` 순서 보장 ISO 표준 c + + 언어 이외의 메모리를 추가 하는 의미 체계입니다. 의미 체계를 획득 해제 volatile 액세스에서 보장 됩니다. 그러나이 옵션에는 또한 ARM 및 다른 약한 메모리 정렬 아키텍처에 상당한 오버 헤드를 추가할 수 있는 하드웨어 메모리 장벽을 생성 하도록 컴파일러에 강제로 합니다. 기본 해석 컴파일러를 ARM 제외한 모든 플랫폼을 대상으로 하는 경우 이것이 `volatile`합니다.

## <a name="remarks"></a>설명

사용 하는 것이 좋습니다 **/volatile:iso** 스레드 간에 공유 되는 메모리를 처리할 때 컴파일러 내장 형식 및 명시적 동기화 기본 형식입니다. 자세한 내용은 참조 [휘발성](../../cpp/volatile-cpp.md)합니다.

를 기존 코드 이식 하거나 프로젝트 중에이 옵션을 변경 하는 경우 경고를 사용 하도록 설정 하려면 유용할 수 있습니다 [c 4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) 의미 체계의 차이 영향을 받는 코드 위치를 식별 하기.

없는 `#pragma` 이 옵션을 제어와 동일 합니다.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>Visual Studio에서 컴파일러 옵션은 /volatile 설정 하려면

1. 열기는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 에 **추가 옵션** 상자에서 추가 **/volatile:iso** 또는 **/volatile:ms** 선택한 후 **확인** 또는 **적용** 변경 내용을 저장 합니다.

## <a name="see-also"></a>참고 항목

[volatile](../../cpp/volatile-cpp.md)  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
