---
title: "MFC 응용 프로그램의 지역화된 리소스: 위성 DLL | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], MFC 지역화"
  - "지역화[C++], MFC 리소스"
  - "지역화된 리소스[C++]"
  - "MFC DLL[C++], 지역화"
  - "여러 언어 지원[C++]"
  - "리소스 전용 DLL[C++]"
  - "리소스 전용 DLL[C++], MFC 응용 프로그램"
  - "리소스[MFC], 지역화"
  - "위성 DLL[C++]"
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC 응용 프로그램의 지역화된 리소스: 위성 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 버전 7.0 이상에서는 여러 언어로 지역화된 응용 프로그램을 만들도록 도와주는 기능인 위성 DLL을 지원합니다.  위성 DLL이란 특정 언어로 지역화된 응용 프로그램의 리소스가 포함된 [리소스 전용 DLL](../build/creating-a-resource-only-dll.md)입니다.  응용 프로그램이 실행될 때 MFC는 환경에 가장 적합한 지역화된 리소스를 자동으로 로드합니다.  예를 들어, 위성 DLL이 두 개인 영어 리소스를 사용하는 응용 프로그램의 경우, 한 DLL에는 프랑스어로 번역된 리소스가 포함되어 있고 다른 DLL에는 독일어로 번역된 리소스가 포함되어 있을 수 있습니다.  응용 프로그램이 영어 시스템에서 실행될 경우에는 영어 리소스를 사용합니다.  그러나 프랑스어 시스템에서 실행되면 프랑스어 리소스를 사용하여 독일어 시스템에서 실행되면 독일어 리소스를 사용합니다.  
  
 To support localized resources in an MFC 응용 프로그램에서 지역화된 리소스를 지원하기 위해 MFC는 특정 언어로 지역화된 리소스를 포함하는 위성 DLL을 로드합니다.  위성 DLL의 이름은 *ApplicationNameXXX*.dll입니다. 여기서 *ApplicationName* 은 MFC를 사용하는 .exe나 .dll이며 *XXX*는 리소스 언어를 나타내는 세 문자 코드입니다\(예: 'ENU' 또는 'DEU'\).  
  
 MFC는 다음 언어 순서로 리소스 DLL을 로드하려고 시도하다가 하나를 찾으면 중단합니다.  
  
1.  \(Windows 2000 이상만 해당\)현재 사용자의 기본 UI 언어\(GetUserDefaultUILanguage\(\) Win32 API가 반환한 값\).  
  
2.  \(Windows 2000 이상만 해당\)특정 보조 언어 없이, 현재 사용자의 기본 UI 언어\(즉, ENC\[영어\(캐나다\)\]는 ENU\[미국 영어\]가  됩니다.\)  
  
3.  시스템의 기본 UI 언어.  Windows 2000 이상 버전의 경우 GetSystemDefaultUILanguage\(\) API가 반환하는 값입니다.  다른 플랫폼의 경우에는 OS 자체의 언어입니다.  
  
4.  특정 보조 언어 없이, 시스템의 기본 UI 언어.  
  
5.  3문자 코드 LOC를 사용한 가장 언어.  
  
 MFC는 위성 DLL을 찾지 못하면 응용 프로그램에 포함된 리소스를 사용합니다.  
  
 예를 들어 응용 프로그램 LangExample.exe가 MFC를 사용하며 Windows 2000 다중 사용자 인터페이스 시스템에서 실행되고 있을 경우 시스템 UI 언어는  ENU\[미국 영어\]이며 현재 사용자의 UI 언어는 FRC\[프랑스어\(캐나다\)\]로 설정됩니다.  MFC는 다음 순서로 DLL을 찾습니다.  
  
1.  LangExampleFRC.dll\(사용자의 UI 언어\).  
  
2.  LangExampleFRA.dll\(보조 언어 없이 사용자의 UI 언어. 이 예에서는 프랑스어\(프랑스\)입니다.  
  
3.  LangExampleENU.dll\(시스템의 UI 언어\).  
  
4.  LangExampleLOC.dll.  
  
 위의 DLL이 하나도 없으면 MFC는 LangExample.exe의 리소스를 사용합니다.  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)   
 [TN057: MFC 구성 요소 지역화](../mfc/tn057-localization-of-mfc-components.md)