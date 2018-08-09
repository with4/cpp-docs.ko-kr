---
title: 문자열 찾기 | Microsoft Docs
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
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 67d3d4ba38563b4716a87d4b57a4753fe1b49e9c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652096"
---
# <a name="finding-a-string"></a>문자열 찾기
문자열 테이블에 하나 이상의 문자열을 검색 하 고 사용할 수 있습니다 [정규식](/visualstudio/ide/using-regular-expressions-in-visual-studio) 사용 하 여 합니다 **파일에서 찾기** 명령 (**편집** 메뉴) 문자열의 모든 인스턴스를 찾을 수 패턴을 일치 하는 합니다.  
  
### <a name="to-find-a-string-in-the-string-table"></a>문자열 테이블에는 문자열을 찾으려면  
  
1.  문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 **편집** 메뉴에서 클릭 **찾기 및 바꾸기**를 선택한 **찾을**합니다.  
  
3.  에 **찾을 내용** 상자, 드롭 다운 목록에서 이전에 검색 문자열을 선택 하거나 찾으려는 문자열의 캡션 텍스트 또는 리소스 식별자를 입력 합니다.  
  
4.  중 하나를 선택 합니다 **찾을** 옵션입니다.  
  
5.  클릭 **다음 찾기**합니다.  
  
    > [!TIP]
    >  파일을 검색할 때 정규식을 사용 하려면 사용 합니다 **파일에서 찾기** 명령입니다. 정규식 패턴과 일치 하거나 오른쪽의 단추 클릭을 입력 합니다 **찾을 내용** 정규 검색 식의 목록을 표시 하려면 상자입니다. 검색 텍스트로 대체 식을이 목록에서를 선택 하면 합니다 **찾을 내용** 상자입니다. 정규식을 사용 하는 경우는 **사용: Regular Expressions** 확인란을 선택 합니다.  
  
 (대상으로 하는 공용 언어 런타임) 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [연습: Windows Forms 지역화](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) 고[연습: ASP.NET에서 지역화에 리소스를 사용 하 여](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)입니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   