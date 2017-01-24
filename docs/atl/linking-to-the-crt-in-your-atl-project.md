---
title: "Linking to the CRT in Your ATL Project | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DllMainCRTStartup"
  - "wWinMainCRTStartup"
  - "WinMainCRTStartup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, C Run-Time library (CRT)"
  - "CRT, linking with ATL"
  - "DllMainCRTStartup method"
  - "WinMainCRTStartup method"
  - "wWinMainCRTStartup method"
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Linking to the CRT in Your ATL Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[C 런타임 라이브러리](../c-runtime-library/crt-library-features.md) \(CRT\) 프로그래밍 ATL 개발 하는 동안 훨씬 더 쉽게 만들 수 있습니다 많은 유용한 기능을 제공 합니다.  모든 ATL 프로젝트에서 CRT 라이브러리에 링크 합니다.  연결 방법의 장단점을 확인할 수 있습니다  [메서드 사용 하는 CRT에 링크의 장단점 및 혜택](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## 프로그램 이미지에 CRT에 링크 효과  
 CRT에 정적으로 연결 하는 경우 CRT에서 코드 실행 이미지에 들어가고 이미지를 실행 하는 시스템에 CRT DLL이 없어도 있이 필요가 없습니다.  CRT에 동적으로 연결 하는 경우 CRT DLL의 코드에 대 한 참조가 이미지에 포함 되지만 코드 자체에 배치 됩니다.  시스템에서 실행 하려면 이미지를 순서 대로 CRT DLL 시스템에 있어야 합니다.  도 동적으로 CRT에 연결할 때, 사용자 코드 정적으로 연결 될 수 있습니다 찾을 수 있습니다 \(예를 들어,  **DllMainCRTStartup**\).  
  
 이미지를 링크할 때는 운영 체제 이미지를 로드 한 후 호출 되는 진입점 명시적 또는 암시적으로 지정 합니다.  DLL에 대 한 기본 진입점입니다  **DllMainCRTStartup**.  것에 대 한 EXE를  **여**.  \/ENTRY 링커 옵션으로 기본값을 재정의할 수 있습니다.  CRT는 구현에 대 한  **DllMainCRTStartup**,  **여**, 및  **wWinMainCRTStartup** \(유니코드 진입점에 대 한 EXE\).  이러한 CRT 제공 진입점은 전역 개체에서 생성자를 호출 하 고 일부 CRT 함수가 사용 되는 다른 데이터 구조를 초기화 합니다.  정적으로 연결 된 경우이 시작 코드 이미지에 약 25k를 추가 합니다.  동적으로 연결 된 대부분의 코드 경우 DLL에 이미지 크기를 작게 유지 됩니다.  
  
 자세한 내용은 링커 항목  [\/ENTRY \(진입점 기호\)](../build/reference/entry-entry-point-symbol.md).  
  
## 최적화 옵션  
 \/OPT:NOWIN98 링커 옵션을 사용 하 여 더 이상 기본 ATL 컨트롤에서 10 K에을 시간에 Windows 98 시스템 로드를 증가 줄일 수 있습니다.  연결 옵션에 대 한 자세한 내용은  [\/opt \(최적화\)로](../build/reference/opt-optimizations.md).  
  
## 참고 항목  
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)   
 [런타임 라이브러리 동작](../build/run-time-library-behavior.md)