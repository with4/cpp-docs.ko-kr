---
title: 미리 정의 된 규칙이 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0a21847bb9363099fa64825b45a90003de053da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369762"
---
# <a name="predefined-rules"></a>미리 정의된 규칙
미리 정의 된 규칙 NMAKE 제공한 명령 및 옵션 매크로 사용합니다.  
  
|규칙|명령|기본<br /><br /> action|Batch<br /><br /> 규칙|Nmake 플랫폼에서 실행 됩니다.|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|. asm.exe|$(AS) $(AFLAGS) $<|ml $<|아니요|x86|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|예|x86|  
|. asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|아니요|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|예|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. c.exe|$(CC) $(CFLAGS) $<|cl $<|no|모두|  
|. c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|예|모두|  
|. cc.exe|$(CC) $(CFLAGS) $<|cl $<|no|모두|  
|. cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|예|모두|  
|. cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|no|all|  
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|예|모두|  
|. cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|no|all|  
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|예|모두|  
|. rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|아니요|모두|  
  
## <a name="see-also"></a>참고 항목  
 [유추 규칙](../build/inference-rules.md)