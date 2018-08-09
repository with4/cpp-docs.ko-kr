---
title: 메뉴 명령과 액셀러레이터 키 연결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e4b1665e54a03bf7d5f4705aaa3d76962ed16a0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649974"
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>메뉴 명령과 액셀러레이터 키 연결
메뉴 명령과 키보드 조합에서 동일한 프로그램 명령을 종종 실행하도록 하려고 합니다. 사용 하 여이 작업을 수행 합니다 **메뉴** 메뉴 명령 및 응용 프로그램의 액셀러레이터 키 테이블의 항목에 동일한 리소스 식별자를 할당 하는 편집기입니다. 그러고 나서 메뉴 명령의 [캡션](../windows/menu-command-properties.md) 을 편집하여 액셀러레이터 키의 이름을 표시합니다.  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>메뉴 명령을 액셀러레이터 키와 연결하려면  
  
1.  **메뉴** 편집기에서 원하는 메뉴 명령을 선택합니다.  
  
2.  [속성 창](/visualstudio/ide/reference/properties-window)에서 액셀러레이터 키 이름을 **캡션** 속성에 추가합니다.  
  
    -   모든 메뉴의 액셀러레이터 키가 왼쪽으로 맞춰 표시되도록 메뉴 캡션 뒤에 탭의 이스케이프 시퀀스(\t)를 입력합니다.  
  
    -   보조 키의 이름을 입력 합니다 (**Ctrl**를 **Alt**, 또는 **Shift**) 뒤에 더하기 기호 (**+**) 및 이름, 문자 또는 추가 키의 기호입니다.  
  
         예를 들어 할당할 **Ctrl**+**O** 에 **열기** 명령을 **파일** 메뉴에서 메뉴 명령의 수정 **캡션** 다음과 같이 표시 되도록 합니다.  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         메뉴 명령에는 **메뉴** 편집기 입력 한 대로 새 캡션이 반영 하도록 업데이트 됩니다.  
  
3.  [액셀러레이터](../windows/adding-an-entry-to-an-accelerator-table.md) 편집기에서 **액셀러레이터 테이블 항목을 만들고** 메뉴 명령과 같은 식별자를 할당합니다. 기억하기 쉬운 키 조합을 사용합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [메뉴에 명령 추가](../windows/adding-commands-to-a-menu.md)   
 [메뉴 편집기](../windows/menu-editor.md)