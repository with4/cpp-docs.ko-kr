---
title: "/MACHINE(대상 플랫폼 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.TargetMachine"
  - "/machine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MACHINE 링커 옵션"
  - "MACHINE 링커 옵션"
  - "-MACHINE 링커 옵션"
  - "맵 파일, 링커 만들기"
  - "대상 플랫폼"
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MACHINE(대상 플랫폼 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## 설명  
 \/MACHINE 옵션은 프로그램의 대상 플랫폼을 지정합니다.  
  
 일반적으로 사용자는 \/MACHINE 옵션을 지정할 필요가 없습니다.  LINK는 .obj 파일에서 컴퓨터 종류를 유추하기 때문입니다.  그러나 일부 경우에는 LINK에서 컴퓨터 종류를 확인하지 못하여 [링커 도구 오류 LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md)을 표시할 수도 있습니다.  이러한 오류가 발생하는 경우에는 \/MACHINE을 지정합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **대상 컴퓨터** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)