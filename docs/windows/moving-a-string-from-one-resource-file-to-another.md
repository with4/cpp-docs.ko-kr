---
title: 다른 리소스 파일 사이의 문자열 이동 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files, moving strings
- string editing, moving strings between resources
- String editor, moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 194a37bf631ab3226ad88208acfcf86a7a7a2926
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603266"
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>리소스 파일 사이의 문자열 이동
### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>다른 리소스 스크립트 파일에서 문자열을 이동 하려면  
  
1.  두.rc 파일에서 문자열 테이블을 엽니다. (자세한 내용은 [보기 리소스는 프로젝트 외부에서 리소스 스크립트 파일 열기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  이동 하려는 문자열을 마우스 오른쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.  
  
3.  대상 커서를 놓고 **문자열 편집기** 창입니다.  
  
4.  문자열을 이동 하려는.rc 파일에서 마우스 오른쪽 단추로 클릭 하 고 선택 **붙여넣기** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  경우는 **ID** 또는 **값** 기존 이동한 문자열 충돌 **ID** 하거나 **값** 에 대상 파일 중 하나는 **ID** 나 **값** 이동한 문자열 변경 합니다. 문자열이 있으면 동일한 **ID**의 **ID** 이동한 문자열 변경 합니다. 문자열이 있으면 동일한 **값**의 **값** 이동한 문자열 변경 합니다.  
  
 (대상으로 하는 공용 언어 런타임) 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [연습: Windows Forms 지역화](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) 고[연습: ASP.NET에서 지역화에 리소스를 사용 하 여](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)입니다.  
  
## <a name="requirements"></a>요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [창 레이아웃 사용자 지정](/visualstudio/ide/customizing-window-layouts-in-visual-studio)   