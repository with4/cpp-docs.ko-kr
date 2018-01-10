---
title: "방법: Visual c + + 프로젝트를 대상 64 비트 x64 구성 플랫폼 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e651d28af3bd8635691d6a54d6c4cca8eb8c160
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-configure-visual-c-projects-to-target-64-bit-x64-platforms"></a>방법: Visual c + + 프로젝트를 대상 64 비트 x64 구성 플랫폼

C + + 응용 프로그램을 64 비트 x64 플랫폼 설정 하려면 Visual Studio IDE에서 프로젝트 구성을 사용할 수 있습니다. 또한 Win32 프로젝트 설정을 64비트 프로젝트 구성에 마이그레이션할 수 있습니다.  
  
### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>64비트 플랫폼을 대상으로 하도록 C++ 응용 프로그램을 설정하려면  
  
1.  구성하려는 C++ 프로젝트를 엽니다.  
  
2.  해당 프로젝트의 속성 페이지를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
    > [!NOTE]
    >  .NET 프로젝트에 있는지 확인 하는 **구성 속성** 에서 선택한 노드 또는 해당 자식 노드 중 하나는  **\<p r o j > 속성 페이지** 대화 상자, 그렇지 않으면는  **Configuration Manager** 단추를 사용할 수 있습니다.  
  
3.  **구성 관리자** 단추를 선택하여 **구성 관리자** 대화 상자를 엽니다.  
  
4.  에 **활성 솔루션 플랫폼** 드롭 다운 목록에서  **\<새로 만들기... >** 옵션을는 **새 솔루션 플랫폼** 대화 상자.  
  
5.  에 **새 플랫폼 입력 또는 선택** 드롭 다운 목록에서 대상 플랫폼을 64 비트 선택 합니다.  
  
    > [!NOTE]
    >  **새 솔루션 플랫폼** 대화 상자에서 **다음에서 설정 복사** 옵션을 사용하여 기존 프로젝트 설정을 새 64비트 프로젝트 구성에 복사할 수 있습니다.  
  
6.  **확인** 단추를 선택합니다. 이전 단계에서 선택한 플랫폼이 **구성 관리자** 대화 상자의 **활성 솔루션 플랫폼** 아래에 표시됩니다.  
  
7.  선택 된 **닫기** 단추는 **Configuration Manager** 대화 상자를 선택한 후는 **확인** 단추는  **\<p r o j > 속성 페이지** 대화 상자.  
  
### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Win32 프로젝트 설정을 64비트 프로젝트 구성에 복사하려면  
  
-   64비트 플랫폼을 대상으로 하도록 프로젝트를 설정하는 동안 **새 솔루션 플랫폼** 대화 상자가 열리는 경우 **다음에서 설정 복사** 드롭다운 목록에서 **Win32**를 선택합니다. 다음 프로젝트 설정이 프로젝트 수준에서 자동으로 업데이트됩니다.  
  
    -   [/MACHINE](../build/reference/machine-specify-target-platform.md) 링커 옵션이 **/MACHINE:X64**로 설정됩니다.  
  
    -   **출력 등록** 이 꺼집니다. 자세한 내용은 [Linker Property Pages](../ide/linker-property-pages.md)을 참조하세요.  
  
    -   **대상 환경** 이 **/env x64**로 설정됩니다. 자세한 내용은 [MIDL Property Pages: General](../ide/midl-property-pages-general.md)을 참조하세요.  
  
    -   **매개 변수 유효성 검사** 가 초기화되어 기본값으로 다시 설정됩니다. 자세한 내용은 [MIDL Property Pages: Advanced](../ide/midl-property-pages-advanced.md)을 참조하세요.  
  
    -   **디버그 정보 형식** 이 Win32 프로젝트 구성에서 **/ZI** 로 설정되면 64비트 프로젝트 구성에서는 **/Zi** 로 설정됩니다. 자세한 내용은 [/Z7, /Zi, /ZI(디버그 정보 형식)](../build/reference/z7-zi-zi-debug-information-format.md)를 참조하세요.  
  
    > [!NOTE]
    >  이러한 프로젝트 속성이 파일 수준에서 재정의된 경우에는 어떠한 속성도 변경되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  

[.NET framework 64 비트 응용 프로그램](/dotnet/framework/64-bit-apps)   
[64 비트 x64 Visual c + + 구성 대상](../build/configuring-programs-for-64-bit-visual-cpp.md)   
[64비트 응용 프로그램 디버그](/visualstudio/debugger/debug-64-bit-applications)