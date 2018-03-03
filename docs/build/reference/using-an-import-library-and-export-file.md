---
title: "가져오기 라이브러리 및 내보내기 파일을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37d77fdc4df7d2e7239b8bba652d8cf8f4bbc997
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-import-library-and-export-file"></a>가져오기 라이브러리 및 내보내기 파일 사용
이러한 프로그램을 링크 하는 명령은 순환 내보내기를 수용 해야 경우 두 개 이상의 프로그램 모두에 내보내기 및 가져오기 서로, 또는 (실행 파일 또는 DLL)의 가져오기도 수행 하는 다른 프로그램으로 내보냅니다 프로그램.  
  
 순환 내보내기 사용 하지 않는 경우, 다른 프로그램에서 내보내기를 사용 하는 프로그램을 연결 하는 경우 내보내는 프로그램에 대 한 가져오기 라이브러리를 지정 해야 합니다. 내보내기 프로그램에 대 한 가져오기 라이브러리 내보내기 해당 프로그램을 연결할 때 만들어집니다. 따라서 내보내는 프로그램을 가져오는 프로그램 먼저 연결 해야 합니다. 예를 들어 TWO.dll 가져오는 경우 ONE.dll에서, 먼저 ONE.dll 연결 하 고 가져오기 라이브러리 ONE.lib 가져옵니다. 그런 다음 TWO.dll 링크할 때 ONE.lib 지정 합니다. 링커 TWO.dll를 만들면 해당 가져오기 라이브러리, TWO.lib도 만듭니다. TWO.lib TWO.dll에서 가져올 하는 프로그램을 링크할 때 사용 합니다.  
  
 그러나 순환 내보내기 상황에서 수 없으면 다른 프로그램에서 가져오기 라이브러리를 사용 하 여 상호 종속적 프로그램의 모든 연결 합니다. TWO.dll ONE.dll도 내보냅니다, TWO.dll에 대 한 가져오기 라이브러리 존재 하지 않습니다 아직 ONE.dll 연결 되는 경우 앞에서 설명한 예제입니다. 순환 내보내기가 있는 경우 가져오기 라이브러리를 만들어 내보내고 프로그램 중 하나에 대 한 파일을 LIB를 사용 해야 합니다.  
  
 먼저, LIB 실행할 프로그램 중 하나를 선택 합니다. LIB 명령에서 모든 개체 및 라이브러리는 프로그램에 대 한 나열 하 고 /def를 지정 프로그램에서 /EXPORT 사양 또는.def 파일을 사용 하는 경우 이러한 항목도 지정 합니다.  
  
 가져오기 라이브러리 (.lib) 및 프로그램에 대 한 내보내기 (.exp) 파일을 만든 후에 다른 프로그램을 링크할 때 가져오기 라이브러리를 사용 합니다. 링크 빌드하는 각 내보내는 프로그램에 대 한 가져오기 라이브러리를 만듭니다. 예를 들어 ONE.dll에 대 한 개체 및 내보내기에 LIB를 실행 하는 경우를 만들고 ONE.lib ONE.exp 합니다. TWO.dll; 링크할 때 이제 ONE.lib을 사용할 수 있습니다. 이 단계는 또한 TWO.lib 가져오기 라이브러리를 만듭니다.  
  
 마지막으로 작업을 시작한 프로그램을 연결 합니다. LINK 명령에서 개체 및.exp 만든 파일을 LIB에서 프로그램 및 가져오기 라이브러리에 대 한 프로그램에 대 한 라이브러리 또는 프로그램에서 사용 하는 내보내기에 대 한 라이브러리를 지정 합니다. 예제를 계속 하려면 ONE.dll에 대 한 링크 명령을 ONE.exp TWO.lib, 뿐만 아니라 개체 및 ONE.dll로 이동 하는 라이브러리를 포함 합니다. LINK 명령;.def 파일 또는 /EXPORT 사양을 지정 하지 마십시오 이러한 하지 되므로 세 키워드가 필요.exp 파일에 내보내기 정의가 포함 되어 있습니다. .Exp 파일을 사용 하 여 연결 하면 링크 가져오기 라이브러리를 만들지 않습니다, 그리고 가정 때문에.exp 파일을 만들 때 생성 되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../../build/reference/working-with-import-libraries-and-export-files.md)