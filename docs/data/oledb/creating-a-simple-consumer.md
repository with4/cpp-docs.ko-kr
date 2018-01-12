---
title: "단순 소비자 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5febdc019f5e575f685e4e93c892b7f5e777b776
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-simple-consumer"></a>단순 소비자 만들기
ATL 프로젝트 마법사 및 ATL OLE DB 소비자 마법사를 사용 하 여 OLE DB 템플릿 소비자를 생성 합니다.  
  
#### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>OLE DB 소비자에 대 한 콘솔 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  프로젝트 형식 창에서 클릭 된 **Visual c + + 프로젝트** 폴더를 마우스 클릭 한 다음는 **Win32 프로젝트** 템플릿 창에서 아이콘입니다. 에 **이름** 상자 예를 들어 프로젝트의 이름을 입력 합니다 **MyCons**합니다.  
  
3.  **확인**을 클릭합니다.  
  
     Win32 프로젝트 마법사가 나타납니다.  
  
4.  에 **응용 프로그램 설정** 페이지에서 **콘솔 응용 프로그램**를 선택한 후 **ATL에 대 한 지원을 추가**합니다.  
  
5.  클릭 **마침** 는 마법사를 닫고 프로젝트를 생성 합니다.  
  
 다음으로, ATL OLE DB 소비자 마법사를 사용 하 여 OLE DB 소비자 개체를 추가 합니다.  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>ATL OLE DB 소비자 마법사를 사용 하 여 소비자를 만들려면  
  
1.  클래스 뷰에서 마우스 오른쪽 단추로 클릭는 `MyCons` 프로젝트.  
  
2.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **클래스 추가**합니다.  
  
     **클래스 추가** 대화 상자가 나타납니다.  
  
3.  범주 창에서 클릭 **Visual c + +**, 클릭는 **ATL OLE DB 소비자** 클릭 한 다음 확인 하 고 템플릿 창에서 아이콘 **열려**합니다.  
  
     ATL OLE DB 소비자 마법사가 나타납니다.  
  
4.  클릭는 **데이터 원본** 단추입니다.  
  
     **데이터 연결 속성** 대화 상자가 나타납니다.  
  
5.  에 **데이터 연결 속성** 대화 상자에서 다음을 수행 합니다.  
  
    -   에 **공급자** 탭, OLE DB 공급자를 지정 합니다.  
  
    -   에 **연결** 탭을 서버에서 서버 이름, 로그온 ID 및 데이터 원본 및 데이터베이스에 대 한 암호를 지정 합니다.  
  
    > [!NOTE]
    >  에 보안 문제가 **암호 저장 허용** 의 기능은 **데이터 연결 속성** 대화 상자. **서버 로그온 정보 입력**, 두 개의 라디오 단추가 있습니다: **Windows NT 통합 보안** 및 **특정 사용자 이름 및 암호를 사용 하 여**합니다.  
  
    > [!NOTE]
    >  선택 하는 경우 **특정 사용자 이름 및 암호를 사용 하 여**, 암호를 저장 하는 옵션이 제공 (사용 하 여는 **암호 저장 허용** 확인란); 그러나이 옵션은 안전 합니다. 선택 하는 것이 좋습니다. **Windows NT 통합 보안**;이 옵션 Windows NT를 사용 하 여 본인 여부를 확인 합니다.  
  
    > [!NOTE]
    >  암호에 대 한 사용자 또는 보안 메커니즘을 제공 하 고 보호 된 위치에 암호를 저장 하는 중간 계층 응용 프로그램을 사용 해야 Windows NT 통합 보안을 사용할 수 없는 경우 (대신 소스 코드에서).  
  
     공급자와 다른 설정을 선택한 후 클릭 **연결 테스트** 이전 대화 상자 페이지에서 선택한 내용을 확인할 수 있습니다. 경우는 **결과** 보고서 상자 `Test connection succeeded`, 클릭 **확인** 데이터 연결을 만들 수 있습니다.  
  
     **데이터베이스 개체 선택** 대화 상자가 나타납니다.  
  
6.  트리 컨트롤을 사용 하 여 테이블, 뷰 또는 저장된 프로시저를 선택 합니다. 이 절차를 목적으로 Northwind 데이터베이스의 Products 테이블을 선택 합니다.  
  
7.  **확인**을 클릭합니다. ATL OLE DB 소비자 마법사 돌아갑니다.  
  
8.  마법사 완료에 대 한 이름을 `Class` 및 **.h 파일** 또는 저장 프로시저 선택한 테이블, 뷰 이름에 따라 합니다. 원하는 경우이 이름을 편집할 수 있습니다.  
  
9. 지우기는 **특성 사용** 마법사에서 사용 하 여 소비자 코드를 만들 수 있도록 확인란 [OLE DB 템플릿 클래스](../../data/oledb/ole-db-consumer-templates-reference.md) 기본값 대신 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)합니다.  
  
10. 아래 **형식**선택, **명령**합니다.  
  
     마법사 만듭니다는 [CCommand](../../data/oledb/ccommand-class.md)-선택 하는 경우 소비자 기반 **명령** 또는 [CTable](../../data/oledb/ctable-class.md)-선택 하는 경우 소비자 기반 **테이블**합니다. 테이블이 나 명령 클래스는 선택된 된 개체의 이름을 딴 하지만 이름을 편집할 수 있습니다.  
  
11. **지원**, 둡니다는 **변경**, **삽입**, 및 **삭제** 상자 선택을 취소 합니다.  
  
     선택 된 **변경**, **삽입**, 및 **삭제** 필요한 경우 변경, 삽입 및 삭제 된 행 집합의 레코드를 합니다. 저장소 데이터에 데이터를 작성 하는 방법에 대 한 자세한 내용은 참조 하십시오 [행 집합 업데이트](../../data/oledb/updating-rowsets.md)합니다.  
  
12. 클릭 **마침** 여 소비자를 만듭니다.  
  
 에 표시 된 것 처럼 명령 클래스 및 사용자 레코드 클래스 마법사 생성 [소비자 마법사 생성 클래스](../../data/oledb/consumer-wizard-generated-classes.md)합니다. 명령 클래스에서 입력 한 이름을 갖고는 `Class` 상자 마법사에 (이 경우 `CProducts`), 사용자 레코드 클래스 형식의 이름을 갖습니다 "*ClassName*접근자" (이 경우 `CProductsAccessor`).  
  
> [!NOTE]
>  마법사에 다음 줄을 Products.h 넣습니다.  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  이 줄 소비자 응용 프로그램이 컴파일되지 않도록 방지 하 고 하드 코드 된 암호에 대 한 연결 문자열을 확인 하도록 합니다. 연결 문자열을 확인 한 후이 줄의 코드를 제거할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)