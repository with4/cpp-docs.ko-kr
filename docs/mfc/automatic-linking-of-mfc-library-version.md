---
title: "MFC 라이브러리 버전 자동 링크 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: defaultlib
dev_langs: C++
helpviewer_keywords:
- defaultlib in MFC
- automatic links [MFC]
- MFC libraries, linking to
- linking [MFC], automatic of MFC library version
- linking [MFC]
- linking [MFC], of MFC
- MFC libraries, versions
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ddc156d8518318a686796a25e89ee84a9a67ee59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="automatic-linking-of-mfc-library-version"></a>MFC 라이브러리 버전 자동 링크
버전 3.0 이전의 MFC 버전(Visual C++ 버전 2.0 이전)의 경우 링커에 대한 라이브러리의 입력 목록에 올바른 버전의 MFC 라이브러리를 수동으로 지정해야 했습니다. MFC 버전 3.0 이상에서는 더 이상 MFC 라이브러리 버전을 직접 지정할 필요가 없습니다. MFC 헤더 파일 올바른 버전의 MFC 라이브러리에 정의 된 값을 기반으로 자동으로 결정 되는 대신, `#define`와 같은 **_DEBUG** 또는 **_UNICODE**합니다. MFC 헤더 파일 추가 **/defaultlib** MFC 라이브러리의 특정 버전에 연결 하 여 링커가 지시문입니다.  
  
 예를 들어 다음과 같은 AFX.H 헤더 파일의 코드 조각은 MFC의 디버그 버전을 사용 중인지 여부에 따라 링커가 MFC의 NAFXCWD.LIB 또는 NAFXCW.LIB 버전으로 링크하도록 지시합니다.  
  
```c++
#ifndef _UNICODE 
#ifdef _DEBUG
#pragma comment(lib, "nafxcwd.lib")
#else
#pragma comment(lib, "nafxcw.lib")
#endif
#else
#ifdef _DEBUG
#pragma comment(lib, "uafxcwd.lib")
#else
#pragma comment(lib, "uafxcw.lib")
#endif
#endif
```  
  
 MFC 헤더 파일은 또한 MFC 라이브러리, Win32 라이브러리, OLE 라이브러리, 샘플로부터 빌드된 OLE 라이브러리, ODBC 라이브러리 등을 포함해서 모든 필수 라이브러리를 링크합니다. Win32 라이브러리에는 Kernel32.Lib, User32.Lib 및 GDI32.Lib가 포함됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 라이브러리 버전](../mfc/mfc-library-versions.md)

