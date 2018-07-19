---
title: C 런타임 오류 R6026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6026
dev_langs:
- C++
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7c8bea41b946db67ce24a52393d87873926f3f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298131"
---
# <a name="c-runtime-error-r6026"></a>C 런타임 오류 R6026
stdio 초기화에 필요한 공간이 부족 합니다.  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 메모리 문제가 있기 때문입니다. 이 오류에 대 한 여러 가지가 있지만 일반적으로 메모리가 매우 부족 상태로 인해 발생 합니다. 응용 프로그램의 버그, Visual c + + 라이브러리를 사용 하 여, 손상 또는 드라이버에 의해도 발생할 수 있습니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   실행 중인 다른 응용 프로그램을 닫거나 메모리를 확보 하기 위해 컴퓨터를 다시 시작 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   응용 프로그램 작동 중이 던 다른 응용 프로그램 또는 드라이버의 최신 설치 하기 전에 사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 제거 하는 새 응용 프로그램 또는 드라이버, 응용 프로그램을 다시 시도 하십시오.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 Microsoft Visual c + + 재배포 가능 패키지의 모든 복사본을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 이 오류는 메모리가 부족 하는 표준 I/O 지원을 C 런타임에서 초기화를 사용할 수 없을 때 발생 합니다. 이 오류는 일반적으로 앱을 시작할 때 발생 합니다. 응용 프로그램 및 드라이버 및 dll을 로드 하는 시작 시 힙 손상 되지 않도록 확인 합니다.