---
title: "Windows 플랫폼 (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility [C++], C run-time libraries
- compatibility [C++], C run-time libraries
- MBCS [C++], Win32 platforms
- operating systems [C++]
- Unicode [C++], Win32 platforms
ms.assetid: 0aacaf45-6dc4-4908-bd52-57abac7b39f6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a5e7898cad7120333bd0549a44931d9e23640c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="windows-platforms-crt"></a>Windows 플랫폼(CRT)

Visual Studio용 C 런타임 라이브러리는 현재 버전의 Windows 및 Windows Server, [!INCLUDE[win8](../build/reference/includes/win8_md.md)], [!INCLUDE[winserver8](../build/reference/includes/winserver8_md.md)], [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/reference/includes/winsvr08_md.md)] 및 Windows Vista를 지원하며 [!INCLUDE[winxp](../build/includes/winxp_md.md)] x86용 SP3(서비스 팩 3), [!INCLUDE[winxp](../build/includes/winxp_md.md)] x64용 SP2(서비스 팩 2) 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] x86 및 x64용 SP2(서비스 팩 2)를 선택적으로 지원합니다. 이 모든 운영 시스템은 Windows 데스크톱 API(Win32)를 지원하며 유니코드 지원을 제공합니다. 또한 모든 Win32 응용 프로그램에서 MBCS(멀티바이트 문자 집합)를 사용할 수 있습니다.

> [!NOTE]
> Visual Studio 2017에서 **C++를 사용한 데스크톱 개발** 작업의 기본 설치에는 [!INCLUDE[winxp](../build/includes/winxp_md.md)] 및 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] 개발 지원이 포함되지 않습니다. Windows XP 플랫폼 도구 세트를 사용하려면 선택적 구성 요소인 **C++용 Windows XP 지원**을 설치해야 합니다.

## <a name="see-also"></a>참고 항목

[호환성](../c-runtime-library/compatibility.md)  
