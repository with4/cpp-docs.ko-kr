---
title: 문자열의 속성 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource identifiers, string properties
- string tables, changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ff0a5fd4bee88fecb26f09eb1c2f20959d4a448
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651586"
---
# <a name="changing-the-properties-of-a-string"></a>문자열 속성 변경
### <a name="to-change-a-string-or-its-identifier"></a>문자열 또는 식별자를 변경 하려면  
  
1.  문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  편집 하 고 두 번 클릭 하려는 문자열을 선택 합니다 **ID**를 **값**, 또는 **캡션** 열입니다. 이제 다음을 수행할 수 있습니다.  
  
    -   선택는 **ID** 에서 합니다 **ID 드롭다운** 목록 또는 형식은 `ID` 직접에서.  
  
    -   다른 숫자를 입력 합니다 **값** 열입니다.  
  
    -   편집을 입력 합니다 **캡션** 열입니다.  
  
        > [!NOTE]
        >  문자열의 속성을 편집할 수도 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
 (대상으로 하는 공용 언어 런타임) 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [연습: Windows Forms 지역화](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) 고[연습: ASP.NET에서 지역화에 리소스를 사용 하 여](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)입니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   