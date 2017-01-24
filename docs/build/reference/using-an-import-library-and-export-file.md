---
title: "가져오기 라이브러리 및 내보내기 파일 사용 | Microsoft Docs"
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
helpviewer_keywords: 
  - "순환 내보내기"
  - "파일 내보내기"
  - "가져오기 라이브러리, using"
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 가져오기 라이브러리 및 내보내기 파일 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램\(실행 파일 또는 DLL\)이 가져오기도 수행하는 다른 프로그램에 내보내기를 수행하는 경우나, 둘 이상의 프로그램이 상호 간에 내보내기와 가져오기를 모두 수행하는 경우, 이 프로그램들을 링크하는 명령은 순환 내보내기를 허용해야 합니다.  
  
 순환 내보내기를 사용하지 않는 경우 다른 프로그램에서 내보내기를 사용하는 프로그램을 링크할 때에는 내보내는 프로그램에 대한 가져오기 라이브러리를 지정해야 합니다.  내보내는 프로그램에 대한 가져오기 라이브러리는 사용자가 내보내는 프로그램을 링크할 때 만들어집니다.  따라서 가져오는 프로그램보다 내보내는 프로그램을 먼저 링크시켜야 합니다.  예를 들어 TWO.dll이 ONE.dll에서 가져오는 경우에는 ONE.dll을 먼저 링크하고 해당 가져오기 라이브러리인 ONE.lib를 가져옵니다.  그런 다음 TWO.dll을 링크할 때 ONE.lib를 지정합니다.  링커는 TWO.dll을 만들 때 해당 가져오기 라이브러리인 TWO.lib도 만듭니다.  TWO.dll에서 가져오는 프로그램을 링크할 때에는 TWO.lib를 사용합니다.  
  
 하지만 순환 내보내기의 경우, 다른 프로그램에서 가져오기 라이브러리를 사용하여 상호 의존적인 프로그램을 모두 링크시킬 수는 없습니다.  앞의 예제에서 TWO.dll이 ONE.dll에 내보내기도 수행하는 경우에는 ONE.dll이 링크될 때 TWO.dll에 대한 가져오기 라이브러리는 아직 존재하지 않게 됩니다.  따라서 순환 내보내기가 있는 경우에는 LIB를 사용하여 가져오기 라이브러리를 만들고 프로그램 중 하나에 대해 파일을 내보내야 합니다.  
  
 먼저, LIB를 실행할 프로그램 중 하나를 선택합니다.  LIB 명령에서, 해당 프로그램의 모든 개체 및 라이브러리를 나열하고 \/DEF를 지정합니다.  해당 프로그램이 .def 파일 또는 \/EXPORT 사양을 사용하는 경우에는 이러한 항목도 지정합니다.  
  
 프로그램에 대한 가져오기 라이브러리\(.lib\)와 내보내기 파일\(.exp\)을 만든 다음에는 다른 프로그램을 링크할 때 이 가져오기 라이브러리를 사용합니다.  LINK는 LINK가 빌드하는 내보내는 프로그램 각각에 대해 가져오기 라이브러리를 만듭니다.  예를 들어 ONE.dll의 개체 및 내보내기에 대해 LIB를 실행하는 경우에는 ONE.lib와 ONE.exp를 만듭니다.  그러면 TWO.dll을 링크할 때 ONE.lib를 사용할 수 있습니다. 이 단계에서는 가져오기 라이브러리 TWO.lib도 만듭니다.  
  
 마지막으로, 이 작업을 시작한 프로그램을 링크합니다.  LINK 명령에서는 해당 프로그램의 개체 및 라이브러리와, LIB가 해당 프로그램에 대해 만든 .exp 파일, 그리고 해당 프로그램이 사용하는 내보내기에 대한 가져오기 라이브러리를 지정합니다.  계속하여 위 예제에서, ONE.dll에 대한 LINK 명령은 ONE.dll에 들어가는 개체 및 라이브러리뿐만 아니라 ONE.exp 및 TWO.lib도 포함합니다.  LINK 명령에서는 .def 파일이나 \/EXPORT 사양을 지정하지 않습니다. 내보내기 정의가 .exp 파일에 포함되기 때문에 .def 파일이나 \/EXPORT 사양이 필요하지 않습니다.  .exp 파일을 사용하여 링크하는 경우 LINK에서는 .exp 파일이 만들어질 때 가져오기 라이브러리가 만들어진다고 가정하여 가져오기 라이브러리를 만들지 않습니다.  
  
## 참고 항목  
 [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../../build/reference/working-with-import-libraries-and-export-files.md)