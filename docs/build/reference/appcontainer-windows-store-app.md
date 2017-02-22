---
title: "/APPCONTAINER(Windows 스토어 앱) | Microsoft Docs"
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
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /APPCONTAINER(Windows 스토어 앱)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커가 응용 프로그램 컨테이너에서 실행해야 하는 실행 가능 이미지를 만드는지 여부를 지정합니다.  
  
## 구문  
  
```  
/APPCONTAINER[:NO]  
```  
  
## 설명  
 기본적으로 \/APPCONTAINER는 해제됩니다.  
  
 이 옵션은 실행 파일을 수정하여 응용 프로그램을 appcontainer 프로세스 격리 환경에서 실행해야 하는지 여부를 나타냅니다.  appcontainer 환경에서 실행해야 하는 응용 프로그램\(예: [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] 응용 프로그램\)에 대해 \/APPCONTAINER를 지정합니다. \(이 옵션은 템플릿에서 [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] 앱을 만들면 Visual Studio에서 자동으로 설정됩니다.\) 데스크톱 응용 프로그램의 경우 \/APPCONTAINER:NO를 지정하거나 옵션을 생략합니다.  
  
 \/APPCONTAINER 옵션은 [!INCLUDE[win8](../../build/includes/win8_md.md)]에서 도입되었습니다.  
  
### Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **명령줄** 속성 페이지를 선택합니다.  
  
5.  **추가 옵션**에 `/APPCONTAINER` 또는 `/APPCONTAINER:NO`를 입력합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)