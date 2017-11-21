---
title: "C 런타임 오류 r 6033이 발생 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6033
dev_langs: C++
helpviewer_keywords: R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ae5eddbce2e590e53e51b132ebbbd9589b385eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6033"></a>C 런타임 오류 r 6033이 발생
네이티브 코드를 초기화 하는 동안이 어셈블리에서 MSIL 코드를 사용 하려고 합니다. 응용 프로그램에서 버그를 나타냅니다. MSIL로 컴파일된 호출의 결과 가능성이 높으며 (/ clr) 함수를 DllMain 또는 기본 생성자에서 합니다.  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 문제가 있기 때문입니다. 이 오류는 응용 프로그램의 버그로 인해 또는 추가 기능이 나 사용 하 여 확장의 버그로 인해 발생할 수 있습니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 제거를 복구 하거나 모든 확장명 또는 추가 기능을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 이 진단 MSIL 명령을 로더 잠금 하는 동안 실행 했음을 나타냅니다. 이 네이티브 c + + /clr 플래그를 사용 하 여 컴파일한 경우 발생할 수 있습니다. 만 관리 코드를 포함 하는 모듈에서 /clr 플래그를 사용 합니다. 자세한 내용은 참조 [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)합니다.