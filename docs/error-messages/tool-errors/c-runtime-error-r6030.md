---
title: "C 런타임 오류 R6030 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6030
dev_langs: C++
helpviewer_keywords: R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 328f4dac5ec772ec7229c7a4b4a21ed408d3ad73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6030"></a>C 런타임 오류 R6030
CRT 초기화 되지 않았습니다.  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 문제가 있기 때문입니다. 이 문제는 특정 보안 소프트웨어 프로그램 또는 프로그램의 버그로 인해 매우 드문 경우에 가장 자주 발생 합니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   보안 소프트웨어가이 문제를 완화 하기 위한 구체적인 지침 있을 수 있습니다. 자세한 내용은 보안 소프트웨어 공급 업체의 웹 사이트를 확인 합니다. 또는 보안 소프트웨어의 업데이트 된 버전을 확인 하거나 다른 보안 소프트웨어를 시도 하십시오.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 이 오류는 C 런타임 (CRT)를 사용 하는 CRT 시작 코드가 실행 되지 않은 경우에 발생 합니다. 링커 스위치 하는 경우이 오류가 발생할 수 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 시작 주소, 일반적으로 기본값을 재정의 하는 데는 **mainCRTStartup**, **wmainCRTStartup** 에 대 한는 EXE가 콘솔 **WinMainCRTStartup** 또는 **wWinMainCRTStartup** Windows EXE에 대 한 또는 **_DllMainCRTStartup** DLL에 대 한 합니다. 위의 함수 중 하나를 시작할 때 호출 하지 않으면 C 런타임 초기화 되지 않습니다. C 런타임 라이브러리에 연결 하 고 일반을 사용 하는 경우 기본적으로 이러한 시작 함수 호출 일반적으로 **주**, **wmain**, **WinMain**, 또는  **DllMain** 진입점입니다.  
  
 다른 프로그램을 특정 DLL 라이브러리 호출 트래핑 코드 주입 기술을 사용 하는 경우이 오류가 발생할 수 이기도 합니다. 침입적 인 보안 프로그램도이 기술을 사용 합니다. 버전의 Visual Studio 2015 하기 전에 Visual c + +에서는 문제를 해결 하기 위해 정적으로 연결 된 CRT 라이브러리를 사용할 수 있지만 보안 및 응용 프로그램 업데이트의 이유로 권장 되지 않습니다. 이 문제를 수정 하면 최종 사용자 작업이 필요할 수 있습니다.