---
title: "Previewing Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.previewing"
  - "vs.resvw.resource.previewing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "resource previews"
  - "code, viewing"
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Previewing Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스 미리 보기를 사용하면 그래픽 리소스를 열지 않고도 볼 수 있습니다.  리소스를 컴파일하고 나면 리소스 식별자가 숫자로 바뀌기 때문에 실행 파일에도 미리 보기를 사용하면 좋습니다.  이러한 숫자 식별자에는 충분한 정보가 제공되지 않기 때문에 리소스 미리 보기를 통해 신속하게 확인할 수 있습니다.  
  
 시각적인 레이아웃을 미리 볼 수 있는 리소스 형식은 다음과 같습니다.  
  
-   비트맵  
  
-   대화 상자  
  
-   아이콘  
  
-   메뉴  
  
-   커서  
  
-   도구 모음  
  
 액셀러레이터 키, 매니페스트, 문자열 테이블 및 버전 정보 리소스의 경우에는 시각적인 미리 보기 기능이 제공되지 않습니다.  
  
### 리소스를 미리 보려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)나 문서 창에서 IDD\_ABOUTBOX와 같은 리소스를 선택합니다.  
  
     **참고** 프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  [속성 창](../Topic/Properties%20Window.md)에서 **속성 페이지** 단추를 클릭합니다.  
  
     \-또는\-  
  
3.  **보기** 메뉴에서 **속성 페이지**를 클릭합니다.  
  
     속성 페이지가 열리고 리소스 미리 보기가 표시됩니다.  리소스 뷰나 문서 창에서 위쪽\/아래쪽 화살표 키를 사용하여 트리 컨트롤을 탐색할 수 있습니다.  속성 페이지가 열려 있으므로 리소스를 선택하여 미리 볼 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Editors](../mfc/resource-editors.md)