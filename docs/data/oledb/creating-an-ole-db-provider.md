---
title: "OLE DB 공급자 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자 템플릿, 공급자 만들기"
  - "OLE DB 공급자, 만들기"
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 공급자 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB 공급자를 만들려면 마법사를 사용하여 ATL COM 프로젝트와 공급자를 만든 다음 OLE DB 템플릿을 사용하여 파일을 수정하는 것이 좋습니다.  공급자를 사용자 지정할 때 필요하지 않은 속성을 주석으로 처리하고 선택적 인터페이스를 추가할 수 있습니다.  
  
 이 기능을 구현하는 기본적인 단계는 다음과 같습니다.  
  
1.  ATL 프로젝트 마법사를 사용하여 기본 프로젝트 파일을 만들고 ATL OLE DB 공급자 마법사를 사용하여 공급자를 만듭니다\(**클래스 추가**의 Visual C\+\+ 폴더에서 **ATL OLEDB 공급자** 선택\).  
  
2.  CMyProviderRS.h에 있는 `Execute` 메서드의 코드를 수정합니다.  예제를 보려면 [OLE DB 공급자로 문자열 읽어들이기](../../data/oledb/reading-strings-into-the-ole-db-provider.md)를 참조하십시오.  
  
3.  MyProviderDS.h, MyProviderSess.h 및 MyProviderRS.h의 속성 맵을 편집합니다.  마법사는 공급자가 구현하는 모든 속성이 포함된 속성 맵을 만듭니다.  속성 맵을 편집한 다음 공급자가 지원할 필요가 없는 속성을 제거하거나 주석으로 처리합니다.  
  
4.  MyProviderRS.h에 있는 PROVIDER\_COLUMN\_MAP을 업데이트합니다.  예제를 보려면 [OLE DB 공급자에 문자열 저장](../../data/oledb/storing-strings-in-the-ole-db-provider.md)을 참조하십시오.  
  
5.  공급자를 테스트할 준비가 되면 공급자 열거 목록에서 공급자를 찾아 테스트할 수 있습니다.  열거 목록에서 공급자를 찾는 테스트 코드 예제는 [CatDB](http://msdn.microsoft.com/ko-kr/003d516b-2bf6-444e-8be5-4ebaa0b66046)와 [DBViewer](http://msdn.microsoft.com/ko-kr/07620f99-c347-4d09-9ebc-2459e8049832) 샘플 또는 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)의 예제를 참조하십시오.  
  
6.  필요하면 추가 인터페이스를 추가합니다.  예제는 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)을 참조하십시오.  
  
    > [!NOTE]
    >  마법사는 기본적으로 OLE DB 수준 0과 호환이 되는 코드를 생성합니다.  응용 프로그램이 수준 0과 호환이 되도록 하려면 코드에서 마법사가 생성한 인터페이스를 제거하지 마십시오.  
  
## 참고 항목  
 [CATDB](http://msdn.microsoft.com/ko-kr/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/ko-kr/07620f99-c347-4d09-9ebc-2459e8049832)