---
title: 메뉴 명령에 대 한 액세스 키를 할당 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4745bd188f42b5df976750f952a91ce0e30a9cd9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645801"
---
# <a name="assigning-access-keys-to-menu-commands"></a>메뉴 명령에 대한 선택키 할당
액세스 키(사용자가 키보드로 메뉴를 선택할 수 있게 하는 니모닉)를 메뉴 및 메뉴 명령에 할당할 수 있습니다.  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>액세스(바로 가기) 키를 메뉴 명령에 할당하려면  
  
1.  앰퍼샌드를 입력 (`&`) 문자 앞에 메뉴 이름이 나 명령 이름 문자를 해당 액세스 키로 지정 합니다. 예를 들어 "& 파일" 집합 **Alt**+**F** 에 대 한 바로 가기 키로는 **파일** Microsoft Windows 용으로 작성 된 응용 프로그램의 메뉴.  
  
     메뉴 항목은 문자의 하나에 바로 가기 키가 할당되는 시각적 표시를 제공합니다. 앰퍼샌드 뒤의 문자에는 밑줄이 표시됩니다(운영 체제에 따라).  
  
    > [!NOTE]
    >  메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **니모닉 확인** 을 선택하여 메뉴의 모든 액세스 키가 고유한지 확인합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 편집기](../windows/menu-editor.md)