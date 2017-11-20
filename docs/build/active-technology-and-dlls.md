---
title: "액티브 기술 및 Dll | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fb97e43f589718f79f64483593cfea870258d9f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="active-technology-and-dlls"></a>액티브 기술 및 DLL
액티브 기술 개체 서버가 완전히 DLL 내 구현 될 수 있습니다. 이러한 종류의 서버 프로세스 서버를 라고 합니다. MFC 지원 하지 않습니다 완전히 종속 프로세스 서버로 비주얼 편집의 모든 기능에 대 한 액티브 기술 컨테이너의 기본 메시지 루프에 후크 할 서버에 대 한 방법도 제공 하지 때문에. MFC는 액셀러레이터 키 및 유휴 시간 처리 하는 컨테이너 응용 프로그램의 메시지 루프에 대 한 액세스를 해야 합니다.  
  
 자동화 서버를 작성 하는 사용자 인터페이스가 없는 경우 해당 서버를 in-process 서버로 만든 DLL에 완전히 저장 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [자동화 서버](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)