---
title: "버전 정보 리소스의 문자열 편집 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.version
dev_langs: C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4547247a2ab9dc5b8ca98aae6838d9891f4ab49f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="editing-a-string-in-a-version-information-resource"></a>버전 정보 리소스의 문자열 편집
### <a name="to-edit-a-string-in-a-version-information-resource"></a>버전 정보 리소스의 문자열을 편집하려면  
  
1.  항목을 한 번 클릭하여 선택하고 다시 클릭하여 편집을 시작합니다. 버전 정보 테이블에서 직접 변경하거나 [속성 창](/visualstudio/ide/reference/properties-window)에서 변경합니다. 변경 내용은 두 위치에 모두 반영됩니다.  
  
     **참고** 버전 정보 편집기에서 **FILEFLAGS** 키를 편집할 때 속성 창에서 .rc 파일에 대한 **디버그**, **개인 빌드**또는 **특수 빌드** 속성을 편집할 수 없습니다.  
  
    -   버전 정보 편집기에서는 **_DEBUG** 빌드 플래그에 따라 리소스 스크립트의 #ifdef를 사용하여 **디버그** 속성을 설정합니다.  
  
    -   **Private Build** 키에 버전 정보 테이블에서 설정된 **값** 이 있으면 속성 창에서 **FILEFLAGS** 키에 해당하는 **개인 빌드** 속성이 **True**가 됩니다. **값** 이 비어 있으면 속성이 **False**가 됩니다. 마찬가지로 버전 정보 테이블의 **Special Build** 키는 **FILEFLAGS** 키에 대한 **특수 빌드** 속성에 연결됩니다.  
  
 키 또는 값 열 머리글을 클릭하여 문자열 블록의 정보 시퀀스를 정렬할 수 있습니다. 이들 머리글은 정보를 선택한 시퀀스로 자동으로 다시 정렬합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](https://msdn.microsoft.com/library/f45fce5x.aspx) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](https://msdn.microsoft.com/library/xbx3z216.aspx)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](https://msdn.microsoft.com/library/h6270d0z.aspx)합니다.  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [버전 정보 편집기](../windows/version-information-editor.md)   
 [버전 정보 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

