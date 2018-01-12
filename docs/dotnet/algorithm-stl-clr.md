---
title: "알고리즘 (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: <cliext/algorithm>
dev_langs: C++
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7dac0e574122342c96b28a2f5ccbeb1ea5088ae9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="algorithm-stlclr"></a>algorithm(STL/CLR)
알고리즘을 수행 하는 STL/CLR 컨테이너 템플릿 함수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <cliext/algorithm>  
```  
  
## <a name="functions"></a>함수  
  
|함수|설명|  
|--------------|-----------------|  
|[adjacent_find(STL/CLR)](../dotnet/adjacent-find-stl-clr.md)|동일한 두 개의 인접 한 요소를 검색 합니다.|  
|[binary_search(STL/CLR)](../dotnet/binary-search-stl-clr.md)|정렬된 된 시퀀스에 지정된 된 값이 포함 되어 있는지를 테스트 합니다.|  
|[copy(STL/CLR)](../dotnet/copy-stl-clr.md)|소스 범위의 앞쪽으로 반복 하는 대상 범위에 값이 복사 합니다.|  
|[copy_backward(STL/CLR)](../dotnet/copy-backward-stl-clr.md)|소스 범위의 뒤쪽으로 반복 하는 대상 범위에 값이 복사 합니다.|  
|[count(STL/CLR)](../dotnet/count-stl-clr.md)|해당 값이 지정된 값과 일치하는 요소의 개수를 반환합니다.|  
|[count_if(STL/CLR)](../dotnet/count-if-stl-clr.md)|해당 값이 지정된 조건과 일치하는 요소의 개수를 반환합니다.|  
|[equal(STL/CLR)](../dotnet/equal-stl-clr.md)|두 범위를 요소 별로 비교합니다.|  
|[equal_range(STL/CLR)](../dotnet/equal-range-stl-clr.md)|순서가 지정 된 시퀀스의 값을 검색 하 고의 지정된 된 요소에 모두 동일한 값을 하위 시퀀스를 구분 하는 두 개의 위치를 반환 합니다.|  
|[fill(STL/CLR)](../dotnet/fill-stl-clr.md)|지정한 범위의 모든 요소에 동일한 새 값을 할당합니다.|  
|[fill_n(STL/CLR)](../dotnet/fill-n-stl-clr.md)|특정 요소로 시작하는 범위에서 지정된 개수의 요소에 새 값을 할당합니다.|  
|[find(STL/CLR)](../dotnet/find-stl-clr.md)|지정된 된 값의 첫 번째 나타나는 위치를 반환합니다.|  
|[find_end(STL/CLR)](../dotnet/find-end-stl-clr.md)|지정 된 시퀀스와 동일한 범위에서 마지막 하위 시퀀스를 반환 합니다.|  
|[find_first_of(STL/CLR)](../dotnet/find-first-of-stl-clr.md)|첫 번째 요소에 지정된 된 범위 중 하나에 대 한 범위를 검색합니다.|  
|[find_if(STL/CLR)](../dotnet/find-if-stl-clr.md)|요소가 지정된 된 조건을 충족 하는 위치 값의 시퀀스의 첫 번째 요소의 위치를 반환 합니다.|  
|[for_each(STL/CLR)](../dotnet/for-each-stl-clr.md)|값의 시퀀스의 각 요소에 지정된 된 함수 개체를 적용 하 고 함수 개체를 반환 합니다.|  
|[generate(STL/CLR)](../dotnet/generate-stl-clr.md)|값의 시퀀스의 각 요소에 함수 개체에 의해 생성 된 값을 할당 합니다.|  
|[generate_n(STL/CLR)](../dotnet/generate-n-stl-clr.md)|지정 된 개수의 요소에 함수 개체에 의해 생성 된 값을 할당 합니다.|  
|[includes(STL/CLR)](../dotnet/includes-stl-clr.md)|하나의 정렬 된 범위가 두 번째 정렬 된 범위에서 모든 요소를 포함 하는지 여부를 테스트 합니다.|  
|[inplace_merge(STL/CLR)](../dotnet/inplace-merge-stl-clr.md)|두 연속 정렬된 범위의 요소를 단일 정렬 범위로 결합합니다.|  
|[iter_swap(STL/CLR)](../dotnet/iter-swap-stl-clr.md)|지정된 반복기의 쌍이 참조하는 두 값을 교환합니다.|  
|[lexicographical_compare(STL/CLR)](../dotnet/lexicographical-compare-stl-clr.md)|두 개의 시퀀스를 요소를 식별 하는 시퀀스는 둘 중 작은 비교 합니다.|  
|[lower_bound(STL/CLR)](../dotnet/lower-bound-stl-clr.md)|지정된 된 값 보다 크거나 같은 값을 갖는 값의 순서가 지정 된 시퀀스에서 첫 번째 요소의 위치를 찾습니다.|  
|[make_heap(STL/CLR)](../dotnet/make-heap-stl-clr.md)|지정된 된 범위에서 요소는 힙에 대 한 첫 번째 요소는 가장 큰 힙으로 변환 합니다.|  
|[max(STL/CLR)](../dotnet/max-stl-clr.md)|두 개체를 비교 하 고 둘 중 큰 값을 반환 합니다.|  
|[max_element(STL/CLR)](../dotnet/max-element-stl-clr.md)|값의 지정된 된 시퀀스에서 가장 큰 요소를 찾습니다.|  
|[merge(STL/CLR)](../dotnet/merge-stl-clr.md)|두 개의 정렬 된 소스 범위에서 모든 요소를 정렬 된 단일 대상 범위로 결합합니다.|  
|[min(STL/CLR)](../dotnet/min-stl-clr.md)|두 개체를 비교 하 고 둘 중 작은 값을 반환 합니다.|  
|[min_element(STL/CLR)](../dotnet/min-element-stl-clr.md)|값의 지정된 된 시퀀스의 가장 작은 요소를 찾습니다.|  
|[mismatch(STL/CLR)](../dotnet/mismatch-stl-clr.md)|두 범위를 요소 별로 비교 하 고 차이가 발생 한 첫 번째 위치를 반환 합니다.|  
|[next_permutation(STL/CLR)](../dotnet/next-permutation-stl-clr.md)|경우 사전순에 따라 다음으로 큰 순열 대체할은 원래 순서 지정 있도록 범위의 요소 순서를 재정렬 합니다.|  
|[nth_element(STL/CLR)](../dotnet/nth-element-stl-clr.md)|정확 하 게 찾습니다 요소의 시퀀스를 분할는 `n`th 요소는 시퀀스의 앞에 있는 모든 요소는 보다 작거나에 설정 되며 그 뒤에 나오는 모든 요소 보다 크거나 같은 되도록 합니다.|  
|[partial_sort(STL/CLR)](../dotnet/partial-sort-stl-clr.md)|지정 된 수의 범위에서 더 작은 요소를 비 내림차순 정렬합니다.|  
|[partial_sort_copy(STL/CLR)](../dotnet/partial-sort-copy-stl-clr.md)|소스 범위의 요소를 정렬 하는 대상 범위에 소스 범위의 요소를 복사 합니다.|  
|[partition(STL/CLR)](../dotnet/partition-stl-clr.md)|단항 조건자를 만족 하는 요소 앞에 야 하는 실패 하는 범위에서 요소를 정렬 합니다.|  
|[pop_heap(STL/CLR)](../dotnet/pop-heap-stl-clr.md)|끝에 힙 앞에서 가장 큰 요소를 이동 하 고 나머지 요소로 새 힙을 구성 합니다.|  
|[prev_permutation(STL/CLR)](../dotnet/prev-permutation-stl-clr.md)|이 특성이 있으면 사전순에 따라 이전으로 큰 순열으로 바뀝니다 원래 순서 지정 되도록 요소의 시퀀스를 다시 정렬 합니다.|  
|[push_heap(STL/CLR)](../dotnet/push-heap-stl-clr.md)|범위의 마지막에 있는 요소를 범위의 이전 요소로 구성된 기존 힙에 추가합니다.|  
|[random_shuffle(STL/CLR)](../dotnet/random-shuffle-stl-clr.md)|시퀀스를 다시 정렬 `N` 중 하나로 범위에 요소 `N`! 가능 배열 중 하나로 재정렬합니다.|  
|[remove(STL/CLR)](../dotnet/remove-stl-clr.md)|나머지 요소의 순서를 방해 하지 않고 지정된 된 범위에서 지정된 된 값을 삭제 하 고 지정 된 값이 없는 새 범위의 끝을 반환 합니다.|  
|[remove_copy(STL/CLR)](../dotnet/remove-copy-stl-clr.md)|나머지 요소의 순서를 방해 하지 않고 지정된 된 값의 요소는 복사 하지를 대상 범위에 소스 범위의 요소를 복사 합니다.|  
|[remove_copy_if(STL/CLR)](../dotnet/remove-copy-if-stl-clr.md)|소스 범위의 요소를 제외 하 고 나머지 요소의 순서를 방해 하지 않고 조건자를 만족 하는 대상 범위로 복사 합니다.|  
|[remove_if(STL/CLR)](../dotnet/remove-if-stl-clr.md)|나머지 요소의 순서를 방해 하지 않고 지정된 된 범위에서 조건자를 만족 하는 요소를 삭제 합니다. 이어야 합니다.|  
|[replace(STL/CLR)](../dotnet/replace-stl-clr.md)|범위에서 새 값으로 지정 된 값과 일치 하는 요소를 바꿉니다.|  
|[replace_copy(STL/CLR)](../dotnet/replace-copy-stl-clr.md)|소스 범위의 요소 바꾸는 새 값으로 지정 된 값과 일치 하는 요소를 대상 범위로 복사 합니다.|  
|[replace_copy_if(STL/CLR)](../dotnet/replace-copy-if-stl-clr.md)|소스 범위의 각 요소를 검사하고 요소가 지정된 조건자를 충족하면 대체하는 동시에 결과를 새 대상 범위로 복사합니다.|  
|[replace_if(STL/CLR)](../dotnet/replace-if-stl-clr.md)|범위의 각 요소를 검사하고 요소가 지정된 조건자를 충족하면 대체합니다.|  
|[reverse(STL/CLR)](../dotnet/reverse-stl-clr.md)|범위 내에서 요소의 순서를 반대로 바꿉니다.|  
|[reverse_copy(STL/CLR)](../dotnet/reverse-copy-stl-clr.md)|소스 범위 내의 요소의 순서를 바꾸는 동시에 대상 범위로 복사 합니다.|  
|[rotate(STL/CLR)](../dotnet/rotate-stl-clr.md)|인접한 두 범위에 있는 요소를 교환합니다.|  
|[rotate_copy(STL/CLR)](../dotnet/rotate-copy-stl-clr.md)|소스 범위 내의 인접한 두 범위의 요소를 교환하고 결과를 대상 범위로 복사합니다.|  
|[search(STL/CLR)](../dotnet/search-stl-clr.md)|대상 범위 내에서 시퀀스의 요소가 지정된 요소 시퀀스와 동일하거나 이진 조건자가 지정한 의미에 따라 지정된 시퀀스의 요소와 동일한 첫 번째 시퀀스를 검색합니다.|  
|[search_n(STL/CLR)](../dotnet/search-n-stl-clr.md)|범위에서 특정 값의 요소가 지정된 수만큼 있거나 이진 조건자가 지정한 해당 값과 관련이 있는 첫 번째 하위 시퀀스를 검색합니다.|  
|[set_difference(STL/CLR)](../dotnet/set-difference-stl-clr.md)|한 정렬된 소스 범위에 속하지만 두 번째 정렬된 소스 범위에 속하지 않는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[set_intersection(STL/CLR)](../dotnet/set-intersection-stl-clr.md)|정렬된 두 소스 범위에 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[set_symmetric_difference(STL/CLR)](../dotnet/set-symmetric-difference-stl-clr.md)|정렬된 두 소스 범위 중 하나에만 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[set_union(STL/CLR)](../dotnet/set-union-stl-clr.md)|정렬된 두 소스 범위 중 하나 이상에 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[sort(STL/CLR)](../dotnet/sort-stl-clr.md)|지정된 범위에 있는 요소를 비내림차순 또는 이진 조건자로 지정한 정렬 기준에 따라 정렬합니다.|  
|[sort_heap(STL/CLR)](../dotnet/sort-heap-stl-clr.md)|힙을 정렬된 범위로 변환합니다.|  
|[stable_partition(STL/CLR)](../dotnet/stable-partition-stl-clr.md)|범위의 요소를 두 개의 연결되지 않은 집합으로 분류하고, 단항 조건자를 만족하는 요소는 만족하지 않는 요소보다 앞에 오도록 하여 동등한 요소의 상대적 관계를 유지합니다.|  
|[stable_sort(STL/CLR)](../dotnet/stable-sort-stl-clr.md)|지정된 범위에 있는 요소를 비내림차순 또는 이진 조건자로 지정한 정렬 기준에 따라 정렬하고 동등한 요소의 상대적 관계를 유지합니다.|  
|[swap(STL/CLR)](../dotnet/swap-stl-clr.md)|두 가지 형식의 개체 사이에서 요소 값을 교환하여 첫 번째 개체의 내용을 두 번째 개체에 할당하고 두 번째 개체의 내용을 첫 번째 개체에 할당합니다.|  
|[swap_ranges(STL/CLR)](../dotnet/swap-ranges-stl-clr.md)|한 범위의 요소를 크기가 동일한 다른 범위의 요소로 교환합니다.|  
|[transform(STL/CLR)](../dotnet/transform-stl-clr.md)|두 소스 범위에서 요소 쌍에 또는 소스 범위에 있는 각 요소에 지정된 함수 개체를 적용하고 대상 범위에 함수 개체의 반환 값을 복사합니다.|  
|[unique(STL/CLR)](../dotnet/unique-stl-clr.md)|지정된 범위에서 서로 인접한 중복 요소를 제거합니다.|  
|[unique_copy(STL/CLR)](../dotnet/unique-copy-stl-clr.md)|서로 인접한 중복 요소를 제외하고 소스 범위의 요소를 대상 범위로 복사합니다.|  
|[upper_bound(STL/CLR)](../dotnet/upper-bound-stl-clr.md)|지정된 값보다 큰 값을 갖는 정렬된 범위에 있는 첫 번째 요소의 위치를 찾습니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)