---
title: "FreeLibrary 및 AfxFreeLibrary | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs: C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 276d93489a714dda5edd721c532c28c03b3ca41f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary 및 AfxFreeLibrary
DLL 호출에 명시적으로 연결 하는 프로세스는 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) DLL 모듈이 더 이상 필요 없는 경우에 작동 합니다. 이 함수는 모듈의 참조 횟수 및 프로세스의 주소 공간에서의 참조 횟수가 0 바이트인 경우 매핑을 해제 합니다.  
  
 MFC 응용 프로그램에서 사용 하 여 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) 대신 `FreeLibrary` MFC 확장 DLL을 언로드할 수 있습니다. 에 대 한 인터페이스 (함수 프로토타입) `AfxFreeLibrary` 동일 `FreeLibrary`합니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [암시적으로 DLL에 연결 하는 방법](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [사용할 연결 방법을 결정 합니다.](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual c + +의 Dll](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)