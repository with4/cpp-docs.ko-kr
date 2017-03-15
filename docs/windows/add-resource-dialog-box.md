---
title: "리소스 추가 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.insertresource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "리소스[Visual Studio], 추가"
  - "리소스 추가 대화 상자"
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 리소스 추가 대화 상자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 대화 상자는 C\+\+ Windows 데스크톱 응용 프로그램 프로젝트에 리소스를 추가하는 데 사용합니다.  
  
> [!NOTE]
>  이 정보는 Windows 스토어 앱의 리소스에 적용되지 않습니다. 자세한 내용은 [앱 리소스 정의](http://msdn.microsoft.com/ko-kr/476ea844-632c-4467-9ce3-966be1350dd4)를 참조하세요.  
  
 **리소스 형식**  
 만들려는 리소스의 종류를 지정합니다.  
  
 커서와 대화 상자 리소스 범주를 확장하여 추가 리소스를 표시할 수 있습니다. 이러한 리소스는 ...\\Microsoft Visual Studio `version`\\VC\\VCResourceTemplates\\\<LCID\>\\mfc.rct에 있습니다. .rct 파일을 추가하려면 파일을 이 디렉터리에 저장하거나 파일의 [포함 경로](../windows/how-to-specify-include-directories-for-resources.md)를 지정해야 합니다. 그러면 이러한 파일의 리소스가 해당 범주의 두 번째 수준에 표시됩니다. 추가할 수 있는 .rct 파일의 수는 미리 설정된 제한이 없습니다.  
  
 트리 컨트롤의 최상위 수준에 있는 리소스는 Visual Studio에서 제공하는 기본 리소스입니다.  
  
 **새로 만들기**  
 **리소스 형식** 상자에서 선택한 형식을 기반으로 리소스를 만듭니다. 리소스가 해당 편집기에서 열립니다. 예를 들어 대화 상자 리소스를 만들 경우 [대화 상자 편집기](../mfc/dialog-editor.md)에서 열립니다.  
  
 **가져오기**  
 **가져오기** 대화 상자를 열어 현재 프로젝트로 가져올 리소스를 지정합니다. 비트맵, 아이콘, 커서, HTML 리소스 파일, 사운드\(.WAV\) 리소스 파일 또는 사용자 지정 리소스 파일을 가져올 수 있습니다.  
  
 **사용자 지정**  
 새 사용자 지정 리소스를 만들 수 있는 [새 사용자 지정 리소스 대화 상자](../windows/new-custom-resource-dialog-box.md)를 엽니다. 사용자 지정 리소스는 바이너리 편집기에서만 편집할 수 있습니다.  
  
## 요구 사항  
 없음  
  
## 참고 항목  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)