---
title: "/MANIFESTINPUT(매니페스트 입력 지정) | Microsoft Docs"
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
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /MANIFESTINPUT(매니페스트 입력 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이미지에 포함된 매니페스트에 포함할 매니페스트 입력 파일을 지정합니다.  
  
## 구문  
  
```c#  
/MANIFESTINPUT:filename  
```  
  
#### 매개 변수  
 `filename`  
 포함된 매니페스트에 포함할 매니페스트 파일입니다.  
  
## 설명  
 **\/MANIFESTINPUT** 옵션은 실행 가능한 이미지에서 포함된 매니페스트를 만들기 위해 입력된 파일의 경로를 지정합니다.  매니페스트 입력 파일이 여러 개 있으면 각 입력 파일당 하나씩 스위치를 여러 번 사용합니다.  매니페스트 입력 파일이 병합되어 포함된 매니페스트를 만듭니다.  이 옵션은 **\/MANIFEST:EMBED** 옵션이 필요합니다.  
  
 이 옵션은 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]에서 직접 설정할 수 없습니다.  대신 프로젝트의 **추가 매니페스트 파일** 속성을 사용하여 포함할 추가 매니페스트 파일을 지정합니다.  자세한 내용은 [\<Projectname\> 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 입력 및 출력](../../ide/input-and-output-manifest-tool.md)을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)