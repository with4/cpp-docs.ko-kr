---
title: 'MFC 응용 프로그램의 지역화 된 리소스: 위성 Dll | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0740f567f17c8d44069211274ab1a4c66da311c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC 응용 프로그램의 지역화된 리소스: 위성 DLL
MFC 버전 7.0 이상 위성 Dll에 여러 언어로 지역화 된 응용 프로그램을 만드는 데 도움이 되는 기능에 대 한 향상 된 지원을 제공 합니다. 위성 DLL이는 [리소스 전용 DLL](../build/creating-a-resource-only-dll.md) 특정 언어에 대 한 지역화 된 응용 프로그램의 리소스를 포함 하 합니다. 응용 프로그램이 실행, MFC는 환경에 대 한 가장 적절 한 지역화 된 리소스를 자동으로 로드 합니다. 예를 들어 영어 리소스 두 위성 Dll에 코드 및 기타는 독일어로 번역을 포함 하 여 리소스의 프랑스어 번역이 포함 된 하나를 사용 하는 응용 프로그램에 있을 수 있습니다. 응용 프로그램은 영어 언어 시스템에서 실행 되는 영어 리소스 사용 합니다. 프랑스 리소스만 사용 하 여 시스템 프랑스어인을 실행 하는 경우 독일어 시스템을 실행 하는 경우에 독일 리소스 사용 합니다.  
  
 위성 DLL을 로드 하려고 하는 MFC MFC 응용 프로그램에서 지역화 된 리소스를 지원 하기 위해이 특정 언어로 지역화 된 리소스가 들어 있는입니다. 위성 Dll 이름이 지정 된 *ApplicationNameXXX*.dll, 여기서 *ApplicationName* .exe 또는.dll이 MFC를 사용 하 여의 이름 및 *XXX* 언어에 대 한 세 문자로 된 코드는 리소스 (예를 들어 '한국어' 또는 'DEU').  
  
 MFC 발견할 때 중지 순서로 다음 언어에 대 한 리소스 DLL을 로드 하려고 했습니다.  
  
1. 현재 사용자의 기본 UI 언어를 GetUserDefaultUILanguage() Win32 API에서 반환 합니다.  
  
2.  특정 보조 언어 없이 현재 사용자의 기본 UI 언어 (즉, [캐나다 영어] ENC 됨 [미국 한국어 영어])입니다.  
  
3.  시스템의 기본 UI 언어를 GetSystemDefaultUILanguage() API에서 반환 합니다. 다른 플랫폼에서 자체 운영 체제의 언어입니다.  
  
4.  시스템의 기본 UI 언어를 특정 보조 언어 없이입니다.  
  
5.  3 자로 코드 LOC. 가장 언어  
  
 MFC 위성 Dll을 찾을 수 없는 경우 응용 프로그램 자체에 포함 된 리소스를 사용 합니다.  
  
 예를 들어, 응용 프로그램 LangExample.exe MFC를 사용 하 고 여러 사용자 인터페이스 s;에서 실행 되 고 가정 시스템 UI 언어는 한국어 [미국 영어] 현재 사용자의 UI 언어 FRC [캐나다 프랑스어]로 설정 됩니다. MFC는 다음 순서 대로 다음 Dll을 찾습니다.  
  
1.  LangExampleFRC.dll (사용자의 UI 언어)입니다.  
  
2.  LangExampleFRA.dll (이 예에서는 프랑스어 (프랑스)에 보조 언어 없이 사용자의 UI 언어입니다.  
  
3.  LangExampleENU.dll (시스템의 UI 언어)입니다.  
  
4.  LangExampleLOC.dll 합니다.  
  
 이러한 dll은 없는 경우, MFC LangExample.exe의 리소스를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual c + +의 Dll](../build/dlls-in-visual-cpp.md)   
 [TN057: MFC 구성 요소 지역화](../mfc/tn057-localization-of-mfc-components.md)