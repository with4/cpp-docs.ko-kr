---
title: "심각한 오류 C1052 | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1052
dev_langs: C++
helpviewer_keywords: C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b9d7cc04fa863d30829c5484b328effc55125e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1052"></a>심각한 오류 C1052  
  
> 프로그램 데이터베이스 파일 '*filename*', /debug: fastlink;를 사용 하 여 링커에 의해 생성 된 컴파일러 없습니다 이러한 PDB 파일을 업데이트할; 하십시오 삭제 하거나 /Fd를 사용 하 여 다른 PDB 파일 이름 지정  
  
컴파일러는 링커에 의해 생성 된 동일한 프로그램 데이터베이스 (PDB) 파일을 업데이트할 수 없을 때는 [/debug: fastlink](../../build/reference/debug-generate-debug-info.md) 옵션을 지정 합니다. 일반적으로 컴파일러에서 생성 된 PDB 파일 및 링커 생성 PDB 파일 이름이 다릅니다. 그러나 동일한 이름을 사용 하도록 설정 된 경우이 오류가 발생할 수 있습니다.  
  
이 문제를 해결 하려면 컴파일러에서 생성 된 및 링커 생성 PDB 파일에 대해 다른 이름을 만들 수 있습니다 또는 다시 컴파일 전에 PDB 파일을 명시적으로 삭제할 수 있습니다.  
  
사용 하 여 명령줄에서 컴파일러에서 생성 된 PDB 파일 이름을 지정 하는 [/Fd](../../build/reference/fd-program-database-file-name.md) 컴파일러 옵션입니다. IDE의 컴파일러에서 생성 된 PDB 파일 이름을 지정 하려면 엽니다는 **속성 페이지** 및 프로젝트에 대 한 대화 상자는 **구성 속성**, **C/c + +**,  **출력 파일** 페이지에서 설정 된 **프로그램 데이터베이스 파일 이름** 속성입니다. 기본적으로이 속성은 `$(IntDir)vc$(PlatformToolsetVersion).pdb`합니다.  
  
또는 링커 생성 PDB 파일 이름을 설정할 수 있습니다. 사용 하 여 명령줄에서 링커 생성 PDB 파일 이름을 지정 하는 [/PDB](../../build/reference/pdb-use-program-database.md) 링커 옵션입니다. IDE의 링커 생성 PDB 파일 이름을 지정 하려면 엽니다는 **속성 페이지** 및 프로젝트에 대 한 대화 상자는 **구성 속성**, **링커**,  **디버깅** 페이지에서 설정 된 **프로그램 데이터베이스 파일 생성** 속성입니다. 기본적으로이 속성 설정 `$(OutDir)$(TargetName).pdb`합니다.  
