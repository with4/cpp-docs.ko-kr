---
title: "컨테이너: 복합 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compound files [MFC]
- compound documents
- containers [MFC], compound files
- OLE documents [MFC], compound files
- performance [MFC], compound files
- files [MFC], compound
- standardized file structure compound files
- documents [MFC], compound
- documents [MFC], OLE
- OLE containers [MFC], compound files
- access modes for files [MFC]
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 261fcca76b4a5c9a6cb329081028672b2f241576
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="containers-compound-files"></a>컨테이너: 복합 파일
이 문서에서는 구성 요소와 복합 파일의 구현 및 OLE 응용 프로그램에서 복합 파일을 사용 하는 경우의 단점을 설명 합니다.  
  
 복합 파일은 OLE의 필수적인 부분입니다. OLE 문서 저장 및 데이터 전송을 간편 하 게 사용 됩니다. 복합 파일은 액티브 구조적된 저장소 모델의 구현입니다. 일관 된 인터페이스에는 저장소, 스트림 또는 파일 개체를 serialization을 지원 하 존재합니다. 복합 파일에서에서 지원 되는 Microsoft Foundation Class 라이브러리는 클래스 `COleStreamFile` 및 `COleDocument`합니다.  
  
> [!NOTE]
>  복합 파일을 사용 한다고 해 서 OLE 문서 또는 복합 문서에서 정보를 가져오는 것은 아닙니다. 복합 파일은 복합 문서, OLE 문서 및 기타 데이터를 저장 하는 방법 중 하나일 뿐입니다.  
  
##  <a name="_core_components_of_a_compound_file"></a>복합 파일의 구성 요소  
 OLE 구현 복합 파일의 세 가지 개체 유형을 사용 하 여: stream 개체, 저장소 개체 및 `ILockBytes` 개체입니다. 이러한 개체는 다음과 같은 방법으로 표준 파일 시스템의 구성 요소와 비슷합니다.  
  
-   예: 파일, 스트림 개체는 모든 종류의 데이터를 저장합니다.  
  
-   디렉터리의 경우 같은 저장소 개체는 다른 저장소 및 스트림 개체를 포함할 수 있습니다.  
  
-   **LockBytes** 개체는 저장소 개체와 실제 하드웨어 간의 인터페이스를 나타냅니다. 어떤 저장 장치에는 실제 바이트를 쓰는 방법을 결정 하는 **LockBytes** 하드 드라이브 등의 글로벌 메모리 영역, 개체에 액세스 합니다. 에 대 한 자세한 내용은 **LockBytes** 개체 및 `ILockBytes` 인터페이스를 참조는 *OLE Programmer's Reference*합니다.  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a>복합 파일의 장점 및 단점  
 복합 파일에는 사용할 수 없는 파일 저장소의 이전 메서드와 함께 합니다. 다음과 같은 변경 내용이 해당됩니다.  
  
-   증분 파일에 액세스 합니다.  
  
-   파일 액세스 모드입니다.  
  
-   파일 구조 표준화 합니다.  
  
 복합 파일의 단점은-플로피 디스크 저장과 관련 된 큰 크기와 성능 문제-해야 수로 간주 여부를 결정 하려면 응용 프로그램에서 사용 하 합니다.  
  
###  <a name="_core_incremental_access_to_files"></a>파일에 대 한 증분 액세스  
 증분에 대 한 파일 액세스가 복합 파일을 사용 하는 자동 이점도 있습니다. 복합 파일은 "파일 내에서 파일 시스템"으로 볼 수 있습니다, 때문에 전체 파일을 로드 하지 않고도 저장소, 스트림 등 개별 개체 유형이 액세스할 수 있습니다. 사용자가 편집을 위해 새 개체에 액세스 하려면 응용 프로그램에 필요한 시간을 줄이고 크게이. 증분 업데이트를 기반으로 동일한 개념 유사한 이점 제공 합니다. 하나의 개체에 대 한 변경 내용을 저장 하기 위해 전체 파일을 저장 하는 대신 OLE 스트림 또는 저장소 개체는 사용자가 편집을 저장 합니다.  
  
###  <a name="_core_file_access_modes"></a>파일 액세스 모드  
 복합 파일을 사용 하는 복합 파일에서 개체 변경 내용을 디스크에 커밋하는 시점을 결정할 수 있다는 합니다. 파일 액세스 되는, 트랜잭션 또는 직접, 모드 변경 내용이 커밋된 결정 합니다.  
  
-   트랜잭션된 모드 2 단계 커밋 작업을 사용 하 여 사용자가을 저장 하거나 변경 내용을 취소 될 때까지 이전 클라이언트 암호 및 사용할 수 있는 문서의 새 복사본이 모두를 유지 함으로써 복합 파일에 개체를 변경 해야 합니다.  
  
-   직접 모드를 나중에 실행 취소할 수 없는 현재 수행 됨에 따라 문서의 변경 내용을 통합 합니다.  
  
 액세스 모드에 대 한 자세한 내용은 참조는 *OLE Programmer's Reference*합니다.  
  
###  <a name="_core_standardization"></a>표준화  
 표준화 된 구조 복합 파일의 다른 OLE 응용 프로그램이 실제로 파일을 생성 한 응용 프로그램을 모르는 상태로 OLE 응용 프로그램에서 만든 복합 파일을 통해 검색할 수 있습니다.  
  
###  <a name="_core_size_and_performance_considerations"></a>크기 및 성능 고려 사항  
 복합 파일 저장소 구조와 데이터를 증분 방식으로 저장 하는 기능의 복잡성 때문에이 형식을 사용 하 여 파일 경향이 다른 파일 보다 더 큰 사용 하 여 구조화 되지 않은 또는 저장소 "플랫 파일"입니다. 응용 프로그램는 자주 로드 하 고 파일을 저장 하는 경우 복합 파일을 사용 하 여 파일 크기를 늘리려면 noncompound 파일 보다 훨씬 더 빠르게 발생할 수 있습니다. 복합 파일 커질 수 있으므로 파일에 저장 하 고 플로피 디스크에서 로드에 대 한 액세스 시간도 영향을 받을 수, 속도가 느려질 파일에 있습니다.  
  
 성능에 영향을 주는 또 다른 문제는 복합 파일의 조각화 합니다. 복합 파일의 크기의 차이 파일에서 사용 하는 첫 번째 및 마지막 디스크 섹터에 의해 결정 됩니다. 조각화 된 파일의 공간 데이터를 포함 하지 않는 크기를 계산할 때 계산 되는 많은 영역을 포함할 수 있습니다. 복합 파일의 수명 기간 동안 이러한 영역 삽입 또는 저장소 개체의 삭제 하 여 생성 됩니다.  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a>복합 파일 형식을 사용 하 여 데이터에 대 한  
 파생 된 문서 클래스를 포함 하는 응용 프로그램을 성공적으로 만들기 후 `COleDocument`, 하 주 문서 생성자를 호출 하도록 `EnableCompoundFile`합니다. 응용 프로그램 마법사 OLE 컨테이너 응용 프로그램을 만들면이 호출이 삽입 됩니다.  
  
 에 *OLE Programmer's Reference*, 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034), [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015), 및 [ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨테이너](../mfc/containers.md)   
 [컨테이너: 사용자 인터페이스 문제](../mfc/containers-user-interface-issues.md)   
 [COleStreamFile 클래스](../mfc/reference/colestreamfile-class.md)   
 [COleDocument 클래스](../mfc/reference/coledocument-class.md)
