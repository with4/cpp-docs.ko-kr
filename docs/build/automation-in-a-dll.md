---
title: DLL의 자동화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41c5f31a72cf734296ecb281e0785d415c8043a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360656"
---
# <a name="automation-in-a-dll"></a>DLL의 자동화
MFC DLL 마법사에서 자동화 옵션을 선택 하면 마법사를 다음으로 제공 합니다.  
  
-   시작 개체 정의 언어 (합니다. ODL) 파일  
  
-   Afxole.h의 STDAFX.h 파일에 include 지시문  
  
-   구현에서 `DllGetClassObject` 호출 하는 함수는 **AfxDllGetClassObject** 함수  
  
-   구현에서 `DllCanUnloadNow` 호출 하는 함수는 **AfxDllCanUnloadNow** 함수  
  
-   구현에서 `DllRegisterServer` 호출 하는 함수는 [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) 함수  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [자동화 서버](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)