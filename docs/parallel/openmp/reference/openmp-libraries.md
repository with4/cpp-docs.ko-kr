---
title: "OpenMP 라이브러리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 760e7d138ab71244419ff71960948d4d10f125eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-libraries"></a>OpenMP 라이브러리
Visual c + +의 OpenMP 런타임 라이브러리를 구성 하는.lib 파일에 설명 합니다.  
  
 다음 라이브러리는 Visual c + + OpenMP 런타임 라이브러리 함수를 포함 합니다.  
  
|OpenMP 런타임 라이브러리|특성|  
|------------------------------|---------------------|  
|VCOMP.LIB|다중 스레드, 동적 링크 (VCOMP에 대 한 가져오기 라이브러리입니다. LIB)입니다.|  
|VCOMPD.LIB|다중 스레드, 동적 링크 (VCOMPD에 대 한 가져오기 라이브러리입니다. 덮개) (디버그)|  
  
 컴파일에서 _DEBUG이 정의 하는 경우 `#include omp.h` VCOMPD 소스 코드에 있습니다. LIB 기본 lib이 됩니다. 그렇지 않으면 VCOMP 합니다. LIB이 사용 됩니다.  
  
 사용할 수 있습니다 [/NODEFAULTLIB (라이브러리 무시)](../../../build/reference/nodefaultlib-ignore-libraries.md) 기본 lib를 제거 하 고 사용자가 선택한 lib를 사용 하 여 명시적으로 링크를 합니다.  
  
 OpenMP Dll Visual c + + 재배포 가능 패키지 디렉터리에 있으며 OpenMP를 사용 하는 응용 프로그램과 함께 배포 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 참조](../../../parallel/openmp/reference/openmp-library-reference.md)