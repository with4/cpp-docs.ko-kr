---
title: "링커 입력 파일로 사용하는 .Pdb 파일 | Microsoft Docs"
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
  - ".pdb 파일, 링커 입력으로 사용"
  - "PDB 파일, 링커 입력으로 사용"
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .Pdb 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/Zi 옵션을 사용하여 컴파일한 개체 파일\(.obj\)에는 프로그램 데이터베이스\(PDB\)의 이름이 들어 있습니다.  이 개체의 PDB 파일 이름을 링커에 지정하지 않습니다. LINK에서는 필요한 경우 포함된 이름을 사용하여 PDB를 찾기 때문입니다.  이는 라이브러리에 포함된 디버깅 가능 개체에도 해당됩니다. 디버깅 가능한 라이브러리의 PDB는 해당 라이브러리와 함께 링커에서도 사용할 수 있어야 합니다.  
  
 또한 LINK에서는 PDB를 사용하여 .exe 파일이나 .dll 파일에 대한 디버깅 정보를 보관합니다.  LINK에서는 프로그램을 다시 빌드할 때 PDB를 업데이트하므로 프로그램의 PDB는 출력 파일이며 동시에 입력 파일입니다.  
  
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)