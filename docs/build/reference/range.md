---
title: "-범위 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /RANGE
dev_langs: C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ccca814a388a458513773247f79cecf87fcdeae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="range"></a>/RANGE
Dumpbin /RAWDATA 또는 /DISASM 등의 다른 dumpbin 옵션와 함께 사용할 경우의 출력을 수정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>플래그  
 **vaMin**  
 Dumpbin 작업을 시작 하려는 가상 주소입니다.  
  
 **vaMax** (선택 사항)  
 Dumpbin 작업을 종료 하려는 가상 주소입니다. 지정 하지 않으면 dumpbin 파일의 끝으로 이동 합니다.  
  
## <a name="remarks"></a>설명  
 이미지에 대 한 가상 주소를 보려면 사용 하 여 맵 파일 (RVA + 자료) 이미지에 대 한는 **/DISASM** 또는 **/HEADERS** dumpbin, 또는 Visual Studio 디버거에서 디스어셈블리 창의 옵션입니다.  
  
## <a name="example"></a>예  
 이 예제에서는 **/범위** 의 표시를 수정 하는 데 사용 되는 **/disasm** 옵션입니다. 이 예제에서는 시작 값은 10 진수로 표현 하 고 끝 값 수는 16으로 지정 됩니다.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)