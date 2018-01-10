---
title: "링커 도구 경고 LNK4099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4099
dev_langs: C++
helpviewer_keywords: LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 364c2f9303707328ebf3bdf3284398e6d4f9f0d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4099"></a>링커 도구 경고 LNK4099
'Filename' PDB은 ' 개체/라이브러리 ' 또는 'path;'에서 찾을 수 없습니다. 디버그 정보가 없는 것 처럼 개체를 링크 합니다.  
  
 링커는.pdb 파일을 찾을 수 없습니다. 포함 된 디렉터리에 복사 `object/library`합니다.  
  
 개체 파일을 연관 된.pdb 파일의 이름을 찾으려면:  
  
1.  개체 파일을 사용 하 여 라이브러리에서 추출 [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**합니다.  
  
2.  경로를 사용 하 여.pdb 파일 확인 **/section:.debug$ T /rawdata dumpbin** `objectname` **.obj**합니다.  
  
 으로 컴파일할 수 있습니다 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)pdb를 사용 하거나 제거 하지 않아도 되므로 [/debug](../../build/reference/debug-generate-debug-info.md) 링커 옵션을 연결 하는 개체에 대 한.pdb 파일이 없는 경우.