---
title: '방법: 리소스 복사 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], moving between files
- resources [Visual Studio], copying
- resource files, copying or moving resources between
- resource files, tiling
- .rc files, copying resources between
- rc files, copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb93f90b6d96d679b055893dc13adaa0d3c2e780
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642983"
---
# <a name="how-to-copy-resources"></a>방법: 리소스 복사
변경 하지 않고 다른 리소스 파일에서 복사할 수 또는 할 수 있습니다 [복사 하는 동안 언어 또는 리소스의 상태를 변경](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md)합니다.  
  
 현재 리소스 파일에 기존 리소스 또는 실행 파일에서 리소스를 쉽게 복사할 수 있습니다. 이 위해 동시에 리소스를 포함 하는 두 파일을 열고 및 다른 하나의 파일에서 항목을 끌어 또는 복사 하는 두 파일 사이 붙여 넣습니다. 이 메서드는 실행 파일 (.exe) 뿐만 아니라 리소스 스크립트 (.rc) 파일 및 리소스 템플릿 (.rct) 파일에 대 한 작동합니다.  
  
> [!NOTE]
>  Visual c + + 응용 프로그램에서 사용할 수 있는 샘플 리소스 파일을 포함 합니다. 자세한 내용은 [CLIPART: 공통 리소스](http://msdn.microsoft.com/9bac2891-b6b3-49ec-a287-cec850c707e0)합니다.  
  
 끌어서 놓기 메서드를 사용 하 여 열려 있는.rc 파일 간에 [프로젝트 외부에서](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)합니다.  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>끌어서 놓기 메서드를 사용 하 여 파일 간에 리소스를 복사 하려면  
  
1.  독립 실행형 두 리소스 파일을 엽니다 (자세한 내용은 [는.rc 파일 외부의 프로젝트에서에서 리소스 보기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). 예를 들어 Source1.rc 및 Source2.rc를 엽니다.  
  
2.  내 첫 번째.rc 파일을 복사 하려는 리소스를 클릭 합니다. 예를 들어 `Source1.rc`, 클릭 **IDD_DIALOG1**합니다.  
  
3.  CTRL 키를 누른 채 두 번째.rc 파일의 리소스를 끕니다. 예를 들어 끌어 **IDD_DIALOG1** 에서 `Source1.rc` 하려면 `Source2.rc`합니다.  
  
    > [!NOTE]
    >  리소스를 누르지 않고 끌기 합니다 **Ctrl** 복사 하는 것이 아니라 리소스 키를 누르면 합니다.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>복사를 사용 하 여 리소스를 복사 및 붙여 넣으려면  
  
1.  독립 실행형 두 리소스 파일을 엽니다 (자세한 내용은 [는.rc 파일 외부의 프로젝트에서에서 리소스 보기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). 예를 들어 Source1.rc 및 Source2.rc를 합니다.  
  
2.  리소스를 복사 하려는 소스 파일에서 (예를 들어 `Source1.rc`), 리소스를 마우스 오른쪽 단추로 클릭 하 고 선택 **복사** 바로 가기 메뉴에서.  
  
3.  리소스를 붙여 하려는 리소스 파일을 마우스 오른쪽 단추로 클릭 (예를 들어 `Source2.rc`). 선택할 **붙여넣기** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  및 삭제, 복사, 잘라내기를 끌거나 수 간의 프로젝트에서 리소스 파일에 붙여 넣습니다 (**리소스 뷰**) 및 독립 실행형.rc 파일 (문서 창에서 열기). 이전 버전의 제품에서이 수행할 수 있습니다.  
  
    > [!NOTE]
    >  기호 이름이 나 기존 파일의 값을 사용 하 여 충돌을 방지 하려면 Visual c + + 변경 될 수 있습니다 되는 리소스의 기호 값 또는 기호 이름 및 값 새 파일에 복사 하면 됩니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로젝트 외부에서 리소스 스크립트 파일 열기(독립 실행형)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)