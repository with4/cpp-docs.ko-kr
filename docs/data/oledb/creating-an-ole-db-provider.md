---
title: OLE DB 공급자 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f649b5b4c79c4148d0aed026b044485ca2b1eaa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097109"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB 공급자 만들기
OLE DB 공급자를 만들려면 마법사를 사용 하는 ATL COM 프로젝트와 공급자를 만들고 다음 OLE DB 템플릿을 사용 하 여 파일을 수정 하는 것이 좋습니다. 공급자를 사용자 지정할 때에 필요 하지 않은 속성을 주석 수 있으며 선택적 인터페이스를 추가할 수 있습니다.  
  
 기본 단계는 다음과 같습니다.  
  
1.  ATL 프로젝트 마법사를 사용 하 여 기본 프로젝트 파일을 만들고 ATL OLE DB 공급자 마법사는 공급자를 만들려면 (선택 **ATL OLE DB Provider** Visual c + + 폴더에서 **클래스 추가**).  
  
2.  코드를 수정 하는 `Execute` CMyProviderRS.h에서 메서드. 예를 들어 참조 [OLE DB 공급자로 문자열 읽어들이기](../../data/oledb/reading-strings-into-the-ole-db-provider.md)합니다.  
  
3.  MyProviderDS.h, MyProviderSess.h, 및 MyProviderRS.h 속성 맵을 편집 합니다. 마법사는 공급자가 구현 하는 모든 속성을 포함 하는 속성 맵을 만듭니다. 속성 맵을 돌아가서 제거 하거나 주석 공급자 지 원하는 데 필요 없는 속성으로 처리 합니다.  
  
4.  MyProviderRS.h의 찾을 수 있는 PROVIDER_COLUMN_MAP를 업데이트 합니다. 예를 들어 참조 [OLE DB 공급자에 문자열 저장](../../data/oledb/storing-strings-in-the-ole-db-provider.md)합니다.  
  
5.  공급자를 테스트할 준비가 되 면 공급자 열거 목록에서 공급자를 찾으려고 시도 하 여 테스트할 수 있습니다. 공급자를 찾는 열거형에는 테스트 코드의 예 참조는 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) 및 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) 의 예제에서는 일부 또는 예제 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)합니다.  
  
6.  원하는 추가 인터페이스를 추가 합니다. 예를 들어 참조 [단순한 읽기 전용 공급자 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)합니다.  
  
    > [!NOTE]
    >  기본적으로 마법사는 OLE DB 수준 0과 호환 되는 코드를 생성 합니다. 응용 프로그램 수준 0 규격 유지 되도록 코드에서 마법사에서 생성 된 인터페이스 중 하나를 제거 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)