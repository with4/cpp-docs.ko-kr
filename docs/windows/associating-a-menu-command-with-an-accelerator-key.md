---
title: 메뉴 명령 액셀러레이터 키 연결 | Microsoft Docs
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
ms.openlocfilehash: c4f1aa4b80aec2e7c16485c08d2505695b21f4d5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858090"
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>메뉴 명령과 액셀러레이터 키 연결
메뉴 명령과 키보드 조합에서 동일한 프로그램 명령을 종종 실행하도록 하려고 합니다. 이렇게 하려면 메뉴 편집기를 사용하여 메뉴 명령과 응용 프로그램의 액셀러레이터 테이블에 있는 항목에 동일한 리소스 식별자를 할당합니다. 그러고 나서 메뉴 명령의 [캡션](../windows/menu-command-properties.md) 을 편집하여 액셀러레이터 키의 이름을 표시합니다.  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>메뉴 명령을 액셀러레이터 키와 연결하려면  
  
1.  **메뉴** 편집기에서 원하는 메뉴 명령을 선택합니다.  
  
2.  [속성 창](/visualstudio/ide/reference/properties-window)에서 액셀러레이터 키 이름을 **캡션** 속성에 추가합니다.  
  
    -   모든 메뉴의 액셀러레이터 키가 왼쪽으로 맞춰 표시되도록 메뉴 캡션 뒤에 탭의 이스케이프 시퀀스(\t)를 입력합니다.  
  
    -   보조 키의 이름(**CTRL**, **ALT**또는 **SHIFT**) 다음에 더하기 기호(**+**)를 입력하고 추가 키의 이름, 문자 또는 기호를 입력합니다.  
  
         예를 들어 **CTRL+O** 를 **파일** 메뉴의 **열기** 명령에 할당하려면 메뉴 명령의 **캡션** 을 다음과 같이 표시되도록 수정합니다.  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         메뉴 편집기의 메뉴 명령이 업데이트되고 입력한 대로 새 캡션이 반영됩니다.  
  
3.  [액셀러레이터](../windows/adding-an-entry-to-an-accelerator-table.md) 편집기에서 **액셀러레이터 테이블 항목을 만들고** 메뉴 명령과 같은 식별자를 할당합니다. 기억하기 쉬운 키 조합을 사용합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [메뉴에 명령 추가](../windows/adding-commands-to-a-menu.md)   
 [메뉴 편집기](../windows/menu-editor.md)