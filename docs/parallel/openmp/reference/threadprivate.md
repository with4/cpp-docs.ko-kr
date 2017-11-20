---
title: threadprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: threadprivate
dev_langs: C++
helpviewer_keywords: threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a95212d3774e9befeccbd8f0da3773305041d11c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="threadprivate"></a>threadprivate
변수는 스레드에 private 임을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `var`  
 스레드에 private 변수의 쉼표로 구분 된 목록입니다. `var`전역 또는 네임 스페이스-범위 변수 또는 정적 지역 변수 중 하나 여야 합니다.  
  
## <a name="remarks"></a>설명  
 `threadprivate` 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 참조 [2.7.1 threadprivate 지시문](../../../parallel/openmp/2-7-1-threadprivate-directive.md)합니다.  
  
 `threadprivate` 지시문 기반는 [스레드](../../../cpp/thread.md) `__declspec` 특성;에 대 한 제한 **__declspec (thread)** 적용할 `threadprivate`합니다.  
  
 사용할 수 없는 `threadprivate` 통해 로드 되는 모든 DLL에 [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)합니다.  여기에와 함께 로드 된 Dll [/DELAYLOAD (가져오기 로드 지연)](../../../build/reference/delayload-delay-load-import.md), 사용 **LoadLibrary**합니다.  
  
 사용할 수 있습니다 `threadprivate` 프로세스를 시작할 때 정적으로 로드 된 DLL에 있습니다.  
  
 때문에 `threadprivate` 기반 **__declspec (thread)**, `threadprivate` 변수는 모든 스레드를 병렬 영역에서 생성 된 스레드 팀의 일원인 하는 스레드 뿐 아니라 프로세스의 시작에 존재 합니다.  이 발생할 수 있습니다, 예를 들어 생성자에 대 한 이후 알고 있어야 하려고 수 있는 구현 정보는 `threadprivate` 사용자 정의 형식이 필요 합니다. 그런 다음 종종 더 많은 호출 합니다.  
  
 A `threadprivate` destructable 형식의 변수는 해당 소멸자가 호출을 보장 되지 않습니다.  예:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 사용자가 병렬 영역을 구성 하는 스레드를 종료에 대 한 제어 하지 않습니다.  프로세스가 종료, 프로세스 종료에 대 한 스레드를 받을 수 없습니다 및에 대 한 소멸자가 호출 되지 것입니다 해당 스레드에 있으면 `threaded_var` 끝내을 제외한 모든 스레드에서 (여기서, 기본 스레드).  코드의 적절 한 소멸에서 계산 되지 해야 하므로 `threadprivate` 변수입니다.  
  
## <a name="example"></a>예제  
 사용 하는 예제에 대 한 `threadprivate`, 참조 [개인](../../../parallel/openmp/reference/private-openmp.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)