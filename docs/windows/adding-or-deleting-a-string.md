---
title: "추가 또는 삭제 String | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], adding to string tables
- string tables, deleting strings
- strings [C++], deleting in string tables
- string tables, adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e485e1c689814e63c5a43edba2ded80967d576a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-or-deleting-a-string"></a>문자열 추가 또는 삭제
문자열 편집기를 사용 하 여 문자열 테이블에 새 항목을 신속 하 게 삽입할 수 있습니다. 새 문자열 테이블의 끝에 배치 되 고 사용 가능한 식별자가 지정 됩니다. ID, 값 또는 캡션 속성을 편집할 수 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window) 필요에 따라 합니다.  
  
 문자열 편집기에서는 이미 사용 하는 ID를 사용 하지 않습니다. 사용 중인 이미 ID를 선택 하는 경우 문자열 편집기를 표시 하 고 IDS_STRING58113 일반 고유 ID를 할당 합니다.  
  
### <a name="to-add-a-string-table-entry"></a>문자열 테이블 엔트리를 추가 하려면  
  
1.  해당 아이콘을 두 번 클릭 하 여 문자열 테이블을 엽니다 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  문자열 테이블 내에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새 문자열** 바로 가기 메뉴에서.  
  
3.  에 **문자열** 편집기는 **ID** 장소에서 직접 ID 형식 ID 드롭 다운 목록에서.  
  
4.  편집 된 **값**필요한 경우.  
  
5.  입력에 대 한 항목은 **캡션**합니다.  
  
    > [!NOTE]
    >  Windows 문자열 테이블에서 null 문자열이 허용 되지 않습니다. "문자열을 입력 하십시오가 테이블 엔트리에 대해." 라는 메시지가 나타나면는 null 문자열 문자열 테이블에 항목을 만드는 경우  
  
### <a name="to-delete-a-string-table-entry"></a>문자열 테이블 엔트리를 삭제 하려면  
  
1.  삭제하려는 항목을 선택합니다.  
  
2.  에 **편집** 메뉴를 클릭 하 여 **삭제**합니다.  
  
 \- 또는 -  
  
-   삭제 하 고 선택 하려는 문자열을 마우스 오른쪽 단추로 클릭 **삭제** 바로 가기 메뉴에서.  
  
 \- 또는 -  
  
-   키를 눌러는 **삭제** 키입니다.  
  
 관리 되는 프로젝트 (공용 언어 런타임을 대상으로 프로젝트)에 리소스를 추가 하는 방법에 대 한 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   

