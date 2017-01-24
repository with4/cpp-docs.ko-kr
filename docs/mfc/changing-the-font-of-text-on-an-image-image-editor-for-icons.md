---
title: "Changing the Font of Text on an Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "fonts, changing on an image"
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Font of Text on an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

아래에 나와 있는 절차는 다음 작업을 수행하는 방법에 대한 예입니다.  
  
-   Windows 응용 프로그램에서 아이콘에 텍스트 추가  
  
-   텍스트의 글꼴 조작  
  
### 이미지의 텍스트 글꼴을 변경하려면  
  
1.  C\# Windows Forms 응용 프로그램을 만듭니다.  자세한 내용은 [Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  [Windows Forms 응용 프로그램 템플릿](http://msdn.microsoft.com/ko-kr/1babdebf-ab3f-4a64-a608-98499a5b9cea)에서 프로젝트에 app.ico라는 파일을 기본적으로 추가합니다.  
  
2.  솔루션 탐색기에서 app.ico 파일을 두 번 클릭합니다.  [이미지 편집기](../mfc/image-editor-for-icons.md)가 열립니다.  
  
3.  **이미지** 메뉴에서 **도구**를 선택한 다음 **텍스트 도구**를 선택합니다.  [텍스트 도구 대화 상자](../mfc/text-tool-dialog-box-image-editor-for-icons.md)가 나타납니다.  
  
4.  텍스트 도구 대화 상자의 빈 텍스트 영역에 `C++`를 입력합니다.  이 텍스트는 이미지 편집기에서 app.ico의 왼쪽 위에 있는 크기 조정이 가능한 상자에 나타납니다.  
  
5.  이미지 편집기에서 크기 조정이 가능한 상자를 app.ico의 중앙으로 끌어와서 텍스트를 더 읽기 쉽게 만듭니다.  
  
6.  텍스트 도구 대화 상자에서 **글꼴** 단추를 클릭합니다.  [텍스트 도구 글꼴 대화 상자](../mfc/text-tool-font-dialog-box-image-editor-for-icons.md)가 나타납니다.  
  
7.  텍스트 도구 글꼴 대화 상자의 **글꼴** 목록 상자에 나와 있는 사용 가능한 글꼴 목록에서 **Times New Roman**을 선택합니다.  
  
8.  **글꼴 스타일** 목록 상자에 나와 있는 사용 가능한 글꼴 스타일 목록에서 **굵게**를 선택합니다.  
  
9. **크기** 목록 상자에 나와 있는 사용 가능한 포인트 크기의 목록에서 **10**을 선택합니다.  
  
10. **확인** 단추를 클릭합니다.  텍스트 도구 글꼴 대화 상자가 닫히고 새 글꼴 설정이 텍스트에 적용됩니다.  
  
11. 텍스트 도구 대화 상자에서 **닫기** 단추를 클릭합니다.  텍스트를 둘러싼 크기 조정이 가능한 상자가 이미지 편집기에서 사라집니다.  
  
## 참고 항목  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Toolbar](../mfc/toolbar-image-editor-for-icons.md)