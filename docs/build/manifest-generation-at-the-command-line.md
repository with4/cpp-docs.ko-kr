---
title: "명령줄에서 매니페스트 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bbbee2fc1402a49aa773afc8eb6ae830edaffcc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="manifest-generation-at-the-command-line"></a>명령줄에서 매니페스트 생성
Nmake 또는 유사한 도구를 사용 하 여 명령줄에서 C/c + + 응용 프로그램을 빌드하는 경우 링커는 모든 개체 파일을 처리 하 고 최종 이진 파일을 빌드한 후 매니페스트가 생성 됩니다. 링커 개체 파일에 저장 된 어셈블리 정보를 수집 하 고 최종 매니페스트 파일에이 정보를 결합 합니다. 기본적으로 링커 라는 < binary_name > 파일을 생성 합니다. \<확장 >.manifest을 최종 이진에 설명 합니다. 링커는 이진 매니페스트 파일이 포함 되어 있지 않으며만 외부 파일로 매니페스트를 생성할 수 있습니다. 여러 가지 방법으로 사용 하는 등 최종 이진 파일에 매니페스트를 포함 하는 [매니페스트 도구 (mt.exe)](http://msdn.microsoft.com/library/aa375649) 매니페스트 리소스 파일에 컴파일 또는 합니다. 서명, 특정 규칙 등의 기능이 증분 링크를 사용 하도록 설정 하려면 최종 이진 매니페스트를 포함 하는 경우 수행 해야 하는 것을 기억 하 고 편집 하며 계속 하기는 것이 유용 합니다. 이러한 오류 코드 및 기타 옵션에 설명 되어 [하는 방법: 매니페스트 내는 C/c + + 응용 프로그램을 포함](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) 명령줄에서 빌드하는 경우.  
  
## <a name="see-also"></a>참고 항목  
 [매니페스트](http://msdn.microsoft.com/library/aa375365)   
 [/INCREMENTAL (증분 링크)](../build/reference/incremental-link-incrementally.md)   
 [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [편집 하며 계속 하기](/visualstudio/debugger/edit-and-continue)   
 [ 프로그램의 매니페스트 생성 이해](../build/understanding-manifest-generation-for-c-cpp-programs.md)