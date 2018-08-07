---
title: C 런타임 오류 R6024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6024
dev_langs:
- C++
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcdfee9da378415afe0b88fe6eed18ec8f570d4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302713"
---
# <a name="c-runtime-error-r6024"></a>C 런타임 오류 R6024
_onexit/atexit 테이블에 필요한 공간이 부족  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 메모리 문제가 있기 때문입니다. 이 오류는 일반적으로 메모리가 매우 부족 상태로 인해 사용 하거나 매우 드문 경우 프로그램에서 버그 또는 사용 하는 Visual c + + 라이브러리의 손상이 발생 됩니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   실행 중인 다른 응용 프로그램을 닫거나 메모리를 확보 하기 위해 컴퓨터를 다시 시작 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 Microsoft Visual c + + 재배포 가능 패키지의 모든 복사본을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 이 오류에 대 한 사용 가능한 메모리가 없습니다.이 때문에 발생는 `_onexit` 또는 `atexit` 함수입니다. 이 오류는 메모리 부족 상태로 인해 발생 합니다. 사용자 데이터를 저장 하 고 클린 응용 프로그램을 수행 하는 데 도움이 되는 응용 프로그램 시작 시 미리 할당 하는 중 버퍼 메모리 부족 상태에서 종료를 고려할 수 있습니다.