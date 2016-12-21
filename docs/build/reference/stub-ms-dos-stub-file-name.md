---
title: "/STUB(MS-DOS 스텁 파일 이름) | Microsoft Docs"
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
  - "/stub"
  - "VC.Project.VCLinkerTool.DosStub"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STUB 링커 옵션"
  - "MS-DOS 스텁 파일 이름 링커 옵션"
  - "STUB 링커 옵션"
  - "-STUB 링커 옵션"
  - "Win32[C++], MS-DOS 스텁 프로그램 연결"
  - "Windows API[C++], MS-DOS 스텁 프로그램 연결"
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STUB(MS-DOS 스텁 파일 이름)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STUB:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 MS\-DOS 응용 프로그램입니다.  
  
## 설명  
 \/STUB 옵션은 MS\-DOS 스텁 프로그램을 Win32 프로그램에 연결합니다.  
  
 이 파일이 MS\-DOS에서 실행되면 스텁 프로그램이 호출됩니다.  대개 적절한 메시지가 표시되지만 모든 올바른 MS\-DOS 응용 프로그램을 스텁 프로그램으로 사용할 수 있습니다.  
  
 명령줄에서 콜론\(:\) 뒤에 스텁 프로그램의 *filename*을 지정합니다.  링커에서는 *filename*을 검사한 다음 해당 파일이 실행 파일이 아니면 오류 메시지를 표시합니다.  프로그램은 .exe 파일이어야 하며 .com 파일은 스텁 프로그램으로 사용할 수 없습니다.  
  
 이 옵션을 사용하지 않으면 링커에서는 다음 메시지를 표시하는 기본 스텁 프로그램을 연결합니다.  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 가상 장치 드라이버를 빌드할 때 *filename*을 사용하면 기본 헤더 대신 IMAGE\_DOS\_HEADER 구조체\(WINNT.H에 정의되어 있음\)가 들어 있는 파일 이름이 VXD에서 사용되도록 지정할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)