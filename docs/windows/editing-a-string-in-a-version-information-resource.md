---
title: 버전 정보 리소스의 문자열 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 306359c1479c8c67d6edc08414f601a4b560496e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648105"
---
# <a name="editing-a-string-in-a-version-information-resource"></a>버전 정보 리소스의 문자열 편집
### <a name="to-edit-a-string-in-a-version-information-resource"></a>버전 정보 리소스의 문자열을 편집하려면  
  
1.  항목을 한 번 클릭하여 선택하고 다시 클릭하여 편집을 시작합니다. 변경에 직접 합니다 **버전 정보** 테이블 또는 합니다 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 변경 내용은 두 위치에 모두 반영됩니다.  
  
     > [!NOTE] 
     > 편집 하는 경우는 `FILEFLAGS` 키를 **버전 정보** 편집기를 보면 설정할 수 없습니다는 **디버그**를 **개인 빌드**, 또는 **특수 빌드** 속성 (에 **속성** 창).rc 파일에 대 한 합니다.  
  
    -   **버전 정보** 편집기 설정을 **디버그** 속성을 `#ifdef` 에 따라 리소스 스크립트는 `_DEBUG` 빌드 플래그.  
  
    -   경우는 `Private Build` 키에는 **값** 에서 설정를 **버전 정보** 테이블에 해당 **개인 빌드** 속성 (에 **속성**  창)에 대 한 합니다 `FILEFLAGS` 키는 **True**합니다. **값** 이 비어 있으면 속성이 **False**가 됩니다. 마찬가지로 **Special Build** 키 (에 **버전 정보** 테이블)에 연결 됩니다는 **특수 빌드** 속성에 대 한를 `FILEFLAGS` 키.  
  
 키 또는 값 열 머리글을 클릭하여 문자열 블록의 정보 시퀀스를 정렬할 수 있습니다. 이들 머리글은 정보를 선택한 시퀀스로 자동으로 다시 정렬합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [버전 정보 편집기](../windows/version-information-editor.md)   
 [버전 정보 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)