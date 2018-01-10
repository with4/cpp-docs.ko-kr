---
title: "입 / 출력 처리에 대 한 권장 사항 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc7fbb58aa1ac85c185756eb336737cbaf33a48e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recommendations-for-handling-inputoutput"></a>입력/출력 처리에 대한 권장 사항
파일 기반 I/O 사용 하는지 여부는 다음 의사 결정 트리의 질문에 대답에 따라 달라 집니다.  
  
 **응용 프로그램의 기본 데이터는 디스크 파일에 있는**  
  
-   예, 주 데이터 디스크 파일에 있습니다.  
  
     **응용 프로그램 전체 파일 메모리로 파일 열기에 읽기 및 쓰기 전체 파일 다시 디스크에 파일 저장을**  
  
    -   예: 기본 MFC 문서 환경입니다. 사용 하 여 **CDocument** 직렬화 합니다.  
  
    -   없음:이 경우 일반적으로 파일의 업데이트 트랜잭션 기반 합니다. 트랜잭션 단위로에 파일을 업데이트 하 고 필요 없는 **CDocument** 직렬화 합니다.  
  
-   아니요, 주 데이터 디스크 파일에 상주 하지 않습니다.  
  
     **데이터를 ODBC 데이터 원본에 있는**  
  
    -   예, 데이터를 ODBC 데이터 원본에 있습니다.  
  
         MFC의 데이터베이스 지원을 사용 합니다. 이 경우에 대 한 표준 MFC 구현에 포함 됩니다는 `CDatabase` 개체, 문서에 설명 된 대로 [MFC: 문서 및 뷰를 이용한 데이터베이스 클래스를 사용 하 여](../data/mfc-using-database-classes-with-documents-and-views.md)합니다. 또한 응용 프로그램 읽고 보조 파일을 쓸 수-"는 데이터베이스 뷰 및 파일이 지원" 옵션은 응용 프로그램 마법사의 용도입니다. 이 경우 보조 파일에 대 한 serialization을 사용 합니다.  
  
    -   아니요, 데이터 ODBC 데이터 원본에 상주 하지 않습니다.  
  
         이 경우의 예: 멤버에 ODBC DBMS가 아닌;의 데이터 데이터를 OLE 또는 DDE 등의 다른 메커니즘을 통해 읽기입니다.  
  
         이러한 경우 직렬화를 사용 하지 않는 한 응용 프로그램 열기와 메뉴 항목을 저장 하지 않습니다. 사용 하려는 여전히는 **CDocument** 홈 기반으로 MFC ODBC와 마찬가지로 응용 프로그램 사용 하 여 문서를 저장할 `CRecordset` 개체입니다. 하지만 프레임 워크의 기본 파일 열기/저장 문서 직렬화를 사용 하지 않습니다.  
  
 열기, 저장을 지원 하 고 파일 메뉴에서 명령으로 저장, 프레임 워크에서는 문서 직렬화를 제공 합니다. Serialization을 읽고 클래스에서 파생 된 개체를 포함 하 여 데이터를 쓸 `CObject`에 영구 저장소 이며 일반적으로 디스크 파일입니다. Serialization은 사용 하기 쉬운 및 사용자 요구를 충족 시키지만 하지만 여러 데이터 액세스 응용 프로그램에 적합 하지 않을 수 있습니다. 데이터 액세스 응용 프로그램에는 일반적으로 트랜잭션 단위로에 데이터를 업데이트 합니다. 트랜잭션 보다는 읽기 및 쓰기 전체 데이터 파일을 한 번에 영향을 받는 레코드를 업데이트 합니다.  
  
 Serialization에 대 한 정보를 참조 하십시오. [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Serialization: Serialization과 데이터베이스 입/출력](../mfc/serialization-serialization-vs-database-input-output.md)
