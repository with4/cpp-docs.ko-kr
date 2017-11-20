---
title: "C 런타임 오류 r 6016 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6016
dev_langs: C++
helpviewer_keywords: R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 10bac18ac50b67037e855e4f25e067afd0cb34ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6016"></a>C 런타임 오류 r 6016
스레드 데이터에 대한 공간이 부족합니다.  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 메모리 문제가 있기 때문입니다. 이 오류에 대 한 다양 한 원인 의해 있지만 응용 프로그램에서 버그 메모리 매우 부족 상태로 인해 또는 추가 기능이 나 앱에서 사용 하는 확장의 버그로 인해 발생 되는 경우가 많습니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   실행 중인 다른 응용 프로그램을 닫거나 메모리를 확보 하기 위해 컴퓨터를 다시 시작 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 응용 프로그램을 다시 설치 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 제거를 복구 하거나 추가 기능 또는 응용 프로그램에서 사용 되는 확장을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 프로그램 완료 하려면 운영 체제에서 충분 한 메모리를 받지 못했습니다 때문에이 오류가 발생 한 [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) 또는 `_beginthreadex` 통화 또는 스레드 로컬 저장소에서 초기화 되지 않은 `_beginthread` 또는 `_beginthreadex`합니다.  
  
 새 스레드가 시작되면 라이브러리는 해당 스레드에 대한 내부 데이터베이스를 만들어야 합니다. 데이터베이스가 운영 체제에서 제공한 메모리를 사용하여 확장할 수 없으면 스레드가 시작되지 않으며 호출 프로세스는 중지됩니다. 프로세스에 의해 너무 많은 스레드가 만들어졌거나 스레드 로컬 저장소를 모두 사용한 경우 이러한 현상이 발생할 수 있습니다.  
  
 C 런타임 라이브러리 (CRT)를 호출 하는 실행 파일을 사용 하도록 하는 것이 좋습니다 `_beginthreadex` Windows API를 사용 하지 않고 스레드 만들기에 대 한 `CreateThread`합니다. `_beginthreadex`는 스레드 로컬 저장소의 많은 CRT 함수에 의해 사용되는 내부 정적 저장소를 초기화합니다. `CreateThread`를 사용하여 스레드를 만드는 경우 초기화된 내부 정적 저장소가 필요한 CRT 함수를 호출할 때 CRT는 R6016으로 프로세스를 종료할 수 있습니다.