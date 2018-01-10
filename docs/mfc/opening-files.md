---
title: "파일 열기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ebc650aa4a3f13a0cbc9d9b0026d948d64ae8b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="opening-files"></a>파일 열기
MFC, 파일을 열려면 가장 일반적인 방법은 2 단계 프로세스를입니다.  
  
#### <a name="to-open-a-file"></a>파일을 열려면  
  
1.  경로 또는 사용 권한 플래그를 지정 하지 않고 파일 개체를 만듭니다.  
  
     일반적으로 선언 하 여 파일 개체를 만들는 [CFile](../mfc/reference/cfile-class.md) 스택 프레임에서 변수입니다.  
  
2.  호출 된 [열려](../mfc/reference/cfile-class.md#open) 경로 및 사용 권한 플래그를 제공 하 여 파일 개체에 대 한 멤버 함수입니다.  
  
     반환 값에 대 한 `Open` 파일을 성공적으로 연 경우 0이 아닌 값 또는 0이 됩니다 지정된 된 파일을 열 수 없는 경우. `Open` 멤버 함수는 프로토타입화 다음과 같습니다.  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     Open 플래그 지정 권한이 같은 파일에 대해 원하는 읽기 전용입니다. 가능한 플래그 값 내에서 열거 된 상수의로 정의 되는 `CFile` 으로 한정 되므로 클래스 "`CFile::`"에서 같이 `CFile::modeRead`합니다. 사용 하 여는 `CFile::modeCreate` 파일을 만들려는 경우 플래그를 지정 합니다.  
  
 다음 예제 (이전 파일 경로가 같은 교체) 읽기/쓰기 권한으로 새 파일을 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]  
  
> [!NOTE]
>  이 예제에서는 만들고 파일을 엽니다. 문제가 있는 경우는 `Open` 호출이 반환 될 수는 `CFileException` 마지막 매개 변수를 다음과 같이 개체입니다. `TRACE` 매크로 파일 이름에 대 한 실패의 원인을 나타내는 코드를 인쇄 합니다. 호출할 수 있습니다는 `AfxThrowFileException` 더 자세한 오류 보고 필요한 경우에 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFile 클래스](../mfc/reference/cfile-class.md)   
 [CFile::Open](../mfc/reference/cfile-class.md#open)   
 [파일](../mfc/files-in-mfc.md)

