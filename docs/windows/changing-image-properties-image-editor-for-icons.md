---
title: "Changing Image Properties (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "images [C++], properties"
  - "Image editor [C++], Properties window"
  - "Image editor [C++], image properties"
  - "Properties window, image editor"
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Changing Image Properties (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[속성 창](../Topic/Properties%20Window.md)을 사용하여 이미지 속성을 설정하거나 수정할 수 있습니다.  
  
### 이미지 속성을 변경하려면  
  
1.  **이미지** 편집기에서 이미지를 엽니다.  
  
2.  **속성** 창에서 이미지의 일부 속성이나 모든 속성을 변경합니다.  
  
    |Property|설명|  
    |--------------|--------|  
    |**Colors**|이미지의 색 구성표를 지정합니다.  단색, 16색, 256색, 트루 컬러 중 하나를 선택합니다.  이미 16색 색상표로 이미지를 그렸을 경우 단색을 선택하면 이미지의 색이 흑백으로 대체됩니다.  대비가 항상 유지되는 것은 아닙니다. 예를 들어, 빨강과 녹색이 인접한 영역은 모두 검정으로 바뀝니다.|  
    |**Filename**|이미지 파일의 이름을 지정합니다.  기본적으로 Visual Studio에서는 기본 리소스 식별자\(IDB\_BITMAP1\)에서 처음 네 문자\("IDB\_"\)를 제거한 후 원하는 확장명을 붙여 만든 기본 파일 이름을 지정합니다.  이 예제에서 이미지 파일 이름은 BITMAP1.bmp가 됩니다.  이 파일 이름을 MYBITMAP1.bmp로 변경해도 됩니다.|  
    |**높이**|이미지의 높이를 픽셀 단위로 설정합니다.  기본값은 48입니다.  이 값에 따라 이미지가 잘리거나 기존 이미지 아래에 공백이 추가됩니다.|  
    |**ID**|리소스의 식별자를 설정합니다.  이미지의 경우, Microsoft Visual Studio에서는 기본적으로 사용 가능한 다음 식별자를 시리즈로 지정합니다\(예: IDB\_BITMAP1, IDB\_BITMAP2 등\).  유사한 이름이 아이콘과 커서에 사용됩니다.|  
    |**Palette**|색 속성을 변경합니다.  두 번 클릭하여 색을 선택하고 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)를 표시합니다.  적절한 텍스트 상자에 RGB나 HSL 값을 입력하여 색을 정의합니다.|  
    |**SaveCompressed**|이미지를 압축 형식으로 저장할 것인지 여부를 나타냅니다.  이 속성은 읽기 전용입니다.  Visual Studio에서는 이미지를 압축 형식으로 저장할 수 없으므로 Visual Studio에서 만든 이미지의 경우 이 속성은 **False**가 됩니다.  다른 프로그램에서 만든 압축 이미지를 Visual Studio에서 열면 이 속성이 **True**가 됩니다.  Visual Studio를 사용하여 압축 이미지를 저장하면 압축이 풀리고 이 속성은 **False**로 다시 설정됩니다.|  
    |**너비**|이미지의 너비를 픽셀 단위로 설정합니다.  비트맵의 기본값은 48입니다.  이 값에 따라 이미지가 잘리거나 기존 이미지 오른쪽에 공백이 추가됩니다.|  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)