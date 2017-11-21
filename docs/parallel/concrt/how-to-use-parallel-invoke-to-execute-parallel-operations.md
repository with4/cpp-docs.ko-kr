---
title: "방법: parallel_invoke 병렬 작업 실행을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2190d7809791fbc66f6070eb3ae721ec1bc0a04f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>방법: parallel_invoke를 사용하여 병렬 작업 실행
사용 하는 방법을 보여 주는이 예제는 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 공유 데이터 원본에 여러 작업을 수행 하는 프로그램의 성능을 향상 시키기 위해 알고리즘입니다. 소스를 수정 하는 작업을 하기 때문에 이러한 수 병렬 실행 간단 하 게에서 합니다.  

  
## <a name="example"></a>예제  
 다음 코드 예제에서는 형식 변수를 만들고를 `MyDataType`해당 변수를 초기화 하는 함수를 호출 하 고 다음 해당 데이터에 대해 여러 개의 긴 작업을 수행 합니다.  
  
 [!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]  
  
 경우는 `lengthy_operation1`, `lengthy_operation2`, 및 `lengthy_operation3` 함수를 수정 하지 마십시오는 `MyDataType` 변수, 이러한 함수 수 병렬로 실행 될 추가로 수정 하지 않고 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 동시에 실행 되도록 이전 예제를 수정 합니다. `parallel_invoke` 알고리즘 동시에 각 작업을 실행 하 고 모든 작업이 완료 된 후를 반환 합니다.  
  
 [!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 다운로드 *The Iliad* gutenberg.org에서 Homer 하 여 해당 파일에 대해 여러 작업을 수행 하 고 있습니다. 이 예제에서는 먼저 이러한 작업을 순차적으로 수행 하 고 동시에 동일한 작업을 수행 합니다.  
  
 [!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Downloading 'The Iliad'...  
 
Running serial version... took 953 ms.  
Running parallel version... took 656 ms.  
 
The most common words that have five or more letters are:  
    their (953)  
    shall (444)  
    which (431)  
    great (398)  
    Hector (349)  
    Achilles (309)  
    through (301)  
    these (268)  
    chief (259)  
The longest sequence of words that have the same first letter is:  
    through the tempest to the tented  
The following palindromes appear in the text:  
    spots stops  
    speed deeps  
    keels sleek  
```  
  
 사용 하 여이 예제는 `parallel_invoke` 알고리즘 여러 호출을 동일한 데이터 원본에 대해 작동 하는 함수입니다. 사용할 수는 `parallel_invoke` 뿐 아니라 동일한 데이터에서 작동 하는 동시에 모든 일련의 함수를 호출 하는 알고리즘입니다.  
  
 때문에 `parallel_invoke` 동시에 각 작업 함수를 호출 하는 알고리즘, 성능이 (즉, 처리 하는 경우 런타임에서 각 함수는 별도 프로세서에서)를 완료 하는 데 오랜 시간이 소요 하는 함수에 의해 제한 됩니다. 병렬 사용 가능한 프로세서 수보다 더 많은 작업을 수행 하는이 예제, 하는 경우 각 프로세서에서 여러 작업을 실행할 수 있습니다. 이 경우 성능은 완료 하는 데 오랜 시간이 소요 하는 작업 그룹으로 제한 됩니다.  
  
 이 예에서는 세 가지 작업을 병렬로 수행, 때문에 성능이 향상 세 개 이상의 프로세서가 있는 컴퓨터 기대할 수 없습니다. 더 많은 성능 향상을 위해 더 작은 작업으로 가장 긴 실행 작업을 중단 하 고 동시에 해당 작업을 실행할 수 있습니다.  
  
 사용할 수는 `parallel_invoke` 대신 알고리즘에서 [concurrency:: task_group](reference/task-group-class.md) 및 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 취소에 대 한 지원이 필요 없는 경우 클래스입니다. 사용법을 비교 하는 예제는 `parallel_invoke` 알고리즘과 작업 그룹 참조 [하는 방법: parallel_invoke를 사용 하 여 병렬 정렬 루틴 작성](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `parallel-word-mining.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc /MD/DUNICODE /D_AFXDLL 병렬 단어 mining.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_invoke 함수](reference/concurrency-namespace-functions.md#parallel_invoke)


