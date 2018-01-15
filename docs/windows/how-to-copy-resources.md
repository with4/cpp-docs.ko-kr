---
title: "방법: 리소스 복사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], moving between files
- resources [Visual Studio], copying
- resource files, copying or moving resources between
- resource files, tiling
- .rc files, copying resources between
- rc files, copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ac30e57c0c833f5d26cf9aa8a9ed4ba43946bb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-copy-resources"></a>방법: 리소스 복사
변경 하지 않은 다른 리소스 파일에서 복사할 수 있습니다 수 또는 [복사 하는 동안 언어 또는 리소스의 조건은 변경](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md)합니다.  
  
 현재 리소스 파일에 기존 리소스 또는 실행 파일에서 리소스를 쉽게 복사할 수 있습니다. 이 위해 동시에 리소스를 포함 하는 두 파일을 열고 하 고 다른 한 파일에서 항목을 끌어 또는 복사 및 붙여 두 파일 간에 합니다. 이 메서드는 실행 파일 (.exe) 뿐만 아니라 리소스 스크립트 (.rc) 파일 및 리소스 템플릿 (.rct) 파일에 대 한 작동합니다.  
  
> [!NOTE]
>  Visual c + + 응용 프로그램에서 사용할 수 있는 샘플 리소스 파일을 포함 합니다. 자세한 내용은 참조 [클립 아트: 공용 리소스](http://msdn.microsoft.com/en-us/9bac2891-b6b3-49ec-a287-cec850c707e0)합니다.  
  
 끌어서 놓기 방법을 사용 하 여 열려 있는.rc 파일 간에 [프로젝트 외부에서](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)합니다.  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>끌어서 놓기 방법을 사용 하 여 파일 간에 리소스를 복사 하려면  
  
1.  독립 실행형 두 리소스 파일을 엽니다 (자세한 내용은 참조 [는.rc로 프로젝트에 리소스 보기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). 예를 들어 Source1.rc 및 Source2.rc를 엽니다.  
  
2.  첫 번째.rc 파일 안에 복사 하려는 리소스를 클릭 합니다. 예를 들어 Source1.rc, IDD_DIALOG1를 클릭 합니다.  
  
3.  CTRL 키를 누른 채 두 번째.rc 파일에는 리소스를 끕니다. 예를 들어 IDD_DIALOG1 Source1.rc에서 Source2.rc 끕니다.  
  
    > [!NOTE]
    >  CTRL 키를 누르지 않은 상태로 리소스를 끌면 복사 되지 않고 이동 합니다.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>복사를 사용 하 여 리소스를 복사 및 붙여 넣으려면  
  
1.  독립 실행형 두 리소스 파일을 엽니다 (자세한 내용은 참조 [는.rc로 프로젝트에 리소스 보기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). 예를 들어 Source1.rc 및 Source2.rc를 합니다.  
  
2.  리소스 (예를 들어 Source1.rc) 복사 하려는 소스 파일에서 리소스를 오른쪽 단추로 클릭 하 고 선택 **복사** 바로 가기 메뉴에서.  
  
3.  리소스 (예를 들어 Source2.rc)을 붙여 넣고 싶은는 리소스 파일을 마우스 오른쪽 단추로 클릭 합니다. 선택 **붙여넣기** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  없습니다 끌어 및, 복사, 잘라내기, 놓거나 붙여 (리소스 보기) 프로젝트에 리소스 파일 및 독립 실행형.rc 파일 파일 (문서 창에서 연) 사이입니다. 이전 버전의 제품에서이 수행할 수 있습니다.  
  
    > [!NOTE]
    >  기호 이름이 나 기존 파일의 값과 충돌을 방지 하려면 Visual c + + 변경 될 수 있습니다 리소스의 기호 값 또는 기호 이름 및 값에서 새 파일로 복사 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스 스크립트 파일 (독립 실행형) 프로젝트 외부에서 열기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)