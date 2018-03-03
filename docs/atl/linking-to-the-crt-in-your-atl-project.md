---
title: "ATL 프로젝트에서 CRT에 연결 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DllMainCRTStartup
- wWinMainCRTStartup
- WinMainCRTStartup
dev_langs:
- C++
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 631426fece3960303d67d8929e99c404beaab998
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL 프로젝트에서 CRT에 연결
[C 런타임 라이브러리](../c-runtime-library/crt-library-features.md) (CRT) 만들 수 있는 프로그래밍 훨씬 더 쉽게 ATL 개발 하는 동안 여러 유용한 기능을 제공 합니다. 모든 ATL 프로젝트는 CRT 라이브러리에 연결합니다. 메서드를 연결의 장단점을 확인할 수 있습니다 [메서드 CRT에 대 한 링크를 사용 하는 장점과 단점](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)합니다.  
  
## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>프로그램 이미지에서 CRT에 연결 하는 한 효과  
 CRT에 정적으로 링크 하는 경우 CRT에서 코드는 실행 가능 이미지에 배치 되 고 이미지를 실행 하려면 시스템에 있는 CRT DLL이 있는 필요가 없습니다. CRT에 동적으로 연결 하는 경우 CRT DLL의 코드에 대 한 참조 이미지를 하지만 코드 자체에 배치 됩니다. 지정된 된 시스템에서 실행 하 여 이미지에 대 한 순서로 CRT DLL 해당 시스템에 있어야 합니다. 도 때 동적으로 CRT에 연결할 알게 될 수 있습니다 수 일부 코드 정적으로 연결 될 수 있습니다 (예를 들어 **DllMainCRTStartup**).  
  
 이미지를 연결 하면 명시적 또는 암시적으로 지정 운영 체제 이미지를 로드 한 후에 호출 하는 진입점. 기본 진입점은 DLL에 대 한 **DllMainCRTStartup**합니다. EXE가 **WinMainCRTStartup**합니다. /ENTRY 링커 옵션으로 기본값을 재정의할 수 있습니다. CRT에 대 한 구현을 제공 **DllMainCRTStartup**, **WinMainCRTStartup**, 및 **wWinMainCRTStartup** (유니코드 진입점 EXE에 대 한). 이러한 CRT 제공 진입점에서 전역 개체 생성자를 호출 하 고 일부 CRT 함수에서 사용 되는 기타 데이터 구조를 초기화 합니다. 이 시작 코드는 정적으로 링크 되는 경우 약 25 K 이미지에 추가 합니다. 동적으로 링크 된 DLL의 대부분의 코드 이므로 이미지 크기가 작게 유지 합니다.  
  
 자세한 내용은 링커 항목을 참조 하십시오. [/ENTRY (진입점 기호)](../build/reference/entry-entry-point-symbol.md)합니다.  
  
## <a name="optimization-options"></a>최적화 옵션  
 /OPT:NOWIN98 링커 옵션을 사용 하 여 더 줄일 수을 10k 기본 ATL 컨트롤을 로드 Windows 98 시스템에서 시간이 증가. 연결 옵션에 대 한 자세한 내용은 참조 하십시오. [/OPT (최적화)](../build/reference/opt-optimizations.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLL 및 Visual C++ 런타임 라이브러리 동작](../build/run-time-library-behavior.md)

