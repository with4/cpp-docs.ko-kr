---
title: "심각한 오류 C1510 | Microsoft Docs"
ms.custom: 
ms.date: 04/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1510
dev_langs: C++
helpviewer_keywords: C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d4128580facdc87239d0087fef1cf9eff701854
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1510"></a>심각한 오류 C1510
언어 리소스 clui.dll을 열 수 없습니다.  
  
 컴파일러 언어 리소스 DLL을 로드할 수 없습니다.  
  
이 문제에 대 한 일반적인 원인은 다음 두 가지 있습니다. 32 비트 컴파일러 및 도구를 사용 하 여 링크 하는 동안 2GB 이상의 메모리를 사용 하는 대규모 프로젝트에 대 한이 오류가 표시 될 수 있습니다. 64 비트 Windows 시스템에서 가능한 솔루션은 64 비트 네이티브를 사용 하 여 또는 크로스 컴파일러 및 코드를 생성 하는 도구입니다. 이 64 비트 응용 프로그램에서 사용할 수 있는 더 큰 메모리 공간을 활용 합니다. 32 비트 시스템에서 실행 되므로 32 비트 컴파일러를 사용 해야 하는 경우 일부 경우에 링커에서을 3GB의 사용 가능한 메모리 양을 늘릴 수 있습니다. 자세한 내용은 참조 [4 기가바이트 튜닝: BCDEdit 및 Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) 및 [BCDEdit increaseuserva설정/](https://msdn.microsoft.com/library/ff542202.aspx) 명령입니다.  

다른 일반적인 이유는 손상 되었거나 불완전 한 Visual Studio 설치입니다. 이 경우 복구 하거나 Visual Studio를 다시 설치를 다시 설치를 실행 합니다.  
  