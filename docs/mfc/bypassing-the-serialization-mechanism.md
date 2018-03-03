---
title: "Serialization 메커니즘 건너뛰기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 510e6ed244fb8920c55c4b3ffedcbd0801c3e202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bypassing-the-serialization-mechanism"></a>Serialization 메커니즘 건너뛰기
위에서 설명한 것 처럼 프레임 워크 데이터 읽기 및 쓰기 / 파일에서 기본 방법을 제공 합니다. 보관 개체를 통해 직렬화 할 매우 많은 응용 프로그램의 요구 사항을 만족 합니다. 이러한 응용 프로그램 및 파일을 읽고 메모리에 완전히, 사용자가 파일을 업데이트할 수 있습니다 다음 다시 디스크에 업데이트 된 버전을 기록 합니다.  
  
 그러나 일부 응용 프로그램 데이터에서 매우 다르게 작동 하 고 이러한 응용 프로그램에 대 한 아카이브를 통한 serialization는 적합 합니다. 데이터베이스 프로그램, 큰 파일의 일부만 편집 하는 프로그램, 텍스트 전용 파일을 작성 하는 프로그램 및 데이터 파일을 공유 하는 프로그램을 예로 들 수 있습니다.  
  
 이러한 경우 재정의할 수 있습니다는 [Serialize](../mfc/reference/cobject-class.md#serialize) 함수를 다른 방식으로 파일을 통해는 동작을 조정 하는 [CFile](../mfc/reference/cfile-class.md) 개체 대신 [CArchive](../mfc/reference/carchive-class.md) 개체입니다.  
  
 사용할 수는 **열고**, **읽기**, **쓰기**, **닫기**, 및 `Seek` 클래스의 멤버 함수 `CFile` 파일을 열려면 파일 포인터를 이동 해당 시점에 레코드 (지정 된 바이트 수)를 읽습니다 (검색) 파일에서 특정 시점으로, 사용자를 업데이트 된 레코드 수는 다음 동일한 지점 다시 및 레코드는 파일에 다시 쓰기 검색 합니다. 프레임 워크는 파일을 열고 사용할 수 있습니다는 `GetFile` 클래스의 멤버 함수 `CArchive` 에 대 한 포인터를 가져올 수는 `CFile` 개체입니다. 훨씬 더 정교 하 고 유연한 사용 하기 위해 재정의할 수 있습니다는 [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) 및 [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) 클래스의 멤버 함수 `CWinApp`합니다. 자세한 내용은 클래스를 참조 하십시오. [CFile](../mfc/reference/cfile-class.md) 에 *MFC 참조*합니다.  
  
 이 시나리오에서는 프로그램 `Serialize` 재정의 예를 들어 문서를 닫을 때 최신 상태로 유지 하는 파일 헤더를 읽고 하 게 하려는 경우가 아니면 아무 것도 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 사용](../mfc/using-documents.md)

