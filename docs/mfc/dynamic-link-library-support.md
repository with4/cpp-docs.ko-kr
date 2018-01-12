---
title: "동적 연결 라이브러리 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular MFC DLLs [MFC], project targets as DLLs
- DLLs [MFC], MFC
- NAFXDW.LIB
- MFC DLLs [MFC], regular MFC DLLs
- USRDLLs, DLL support
- NAFXDWD.LIB
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 394c48644c3b5cdc2514fefef2f4451e4098856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dynamic-link-library-support"></a>동적 연결 라이브러리 지원
NAFXCW.lib 및 NAFXCWD.lib 라이브러리 (동적 연결 라이브러리 명명 규칙 테이블에 나열 된 [라이브러리 명명 규칙](../mfc/library-naming-conventions.md)) "MFC 기본 DLL"를 호출 하는 동적 연결 라이브러리에 프로젝트를 만들면 (이전의 "USRDLL") 클래스 라이브러리와 기본 제공 되지 않는 응용 프로그램과 함께 사용할 수 있는 합니다. 이 DLL 지원 MFCx0.DLL과 MFCx0D.DLL (AFXDLL 라고도 함), DLL의 전체 클래스 라이브러리를 포함 하는 같지는 않습니다. 자세한 내용은 참조 [Dll](../build/dlls-in-visual-cpp.md)합니다. DLL 이름 테이블을 참조 하십시오. [MFC Dll에 대 한 명명 규칙](../build/naming-conventions-for-mfc-dlls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 라이브러리 버전](../mfc/mfc-library-versions.md)

