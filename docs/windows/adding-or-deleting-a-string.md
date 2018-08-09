---
title: 추가 또는 삭제 하는 문자열 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93cf3eba3301b0ae000b9f461851b46be592a119
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650285"
---
# <a name="adding-or-deleting-a-string"></a>문자열 추가 또는 삭제
사용 하 여 문자열 테이블에 새 항목을 신속 하 게 삽입할 수 있습니다 합니다 **문자열** 편집기입니다. 새 문자열 테이블의 끝에 배치 되 고 사용 가능한 식별자가 지정 됩니다. 편집할 수 있습니다 합니다 **ID**, **값**, 또는 **캡션** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window) 필요에 따라 합니다.  
  
 합니다 **문자열** 편집기를 사용 하면 이미 사용 하는 ID를 사용 하지 않습니다. ID를 이미 선택 하면 사용에서 된 **문자열** 편집기를 표시 하 고 예를 들어 일반 고유 ID를 할당 `IDS_STRING58113`합니다.  
  
### <a name="to-add-a-string-table-entry"></a>문자열 테이블 항목을 추가 하려면  
  
1.  문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  문자열 테이블 내에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새 문자열** 바로 가기 메뉴에서.  
  
3.  에 **문자열** 편집기를 선택는 **ID** 형식 ID 직접 바로 ID 드롭다운 목록에서.  
  
4.  편집 된 **값**필요한 경우.  
  
5.  항목을 입력 합니다 **캡션**합니다.  
  
    > [!NOTE]
    >  Windows 문자열 테이블에서 null 문자열이 허용 되지 않습니다. "문자열을 입력 하십시오가 테이블 엔트리에 대해."를 묻는 메시지가 나타나면는 null 문자열을 문자열 테이블에서 항목을 만든 경우  
  
### <a name="to-delete-a-string-table-entry"></a>문자열 테이블 항목을 삭제 하려면  
  
1.  삭제하려는 항목을 선택합니다.  
  
2.  에 **편집할** 메뉴에서 클릭 **삭제**합니다.  
  
 \- 또는 -  
  
-   삭제 하 고 선택 하려는 문자열을 마우스 오른쪽 단추로 클릭 **삭제** 바로 가기 메뉴에서.  
  
 \- 또는 -  
  
-   키를 눌러 합니다 **삭제** 키입니다.  
  
 (대상으로 하는 공용 언어 런타임) 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [연습: Windows Forms 지역화](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) 고[연습: ASP.NET에서 지역화에 리소스를 사용 하 여](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)입니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   