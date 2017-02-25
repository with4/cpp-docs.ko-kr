---
title: "&lt;algorithm&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<algorithm>"
  - "std::<algorithm>"
  - "algorithm/std::<algorithm>"
  - "std.<algorithm>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<algorithm> 헤더"
  - "algorithm 헤더[C++]"
  - "표준 C++ 라이브러리, 알고리즘"
ms.assetid: 19f97711-7a67-4a65-8fd1-9a2bd3ca327d
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;algorithm&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

알고리즘을 수행하는 STL\(표준 템플릿 라이브러리\) 컨테이너 템플릿 함수를 정의합니다.  
  
## 구문  
  
```  
(see relevant links below for specific algorithm syntax)  
```  
  
## 설명  
 STL 알고리즘은 다양한 데이터 구조에서 작동하므로 제네릭입니다.  작동할 수 있는 데이터 구조는 `vector`, `list` 등의 STL 컨테이너 클래스 뿐만 아니라, 특정 알고리즘의 요구 사항을 충족하는 요소 배열 및 프로그램 정의 데이터 구조가 있습니다.  STL 알고리즘은 반복기를 통해 간접적으로 컨테이너 요소를 액세스 및 이동하여 이러한 수준의 일반성을 달성합니다.  
  
 일반적으로 시작 또는 끝 위치로 지정하는 STL 알고리즘 프로세스 반복기 범위.  참조 범위는 유효해야 합니다. 즉, 범위 내 모든 포인터를 역참조할 수 있어야 하며 각 범위의 시퀀스 내에서 마지막 위치를 처음부터 증분으로 접근할 수 있어야 합니다.  
  
 STL 알고리즘은 각 STL 컨테이너의 작업 및 멤버 함수로 지원되는 작업을 확장하며, 예를 들어 다른 형식의 컨테이너 개체를 동시에 사용할 수 있습니다.  알고리즘 목적에 대한 정보를 전달하기 위해 두 개의 접미사가 사용되었습니다.  
  
-   `_if` 접미사는 알고리즘이 요소 값 자체가 아닌 요소 값에서 작동하는 함수 개체에 사용됨을 나타냅니다.  `find_if` 알고리즘은 요소 값이 함수 개체에서 지정한 기준을 충족하는 요소를 찾고, `find` 알고리즘은 특정 값을 찾습니다.  
  
-   \_copy 접미사는 알고리즘이 요소 값을 조작할 뿐만 아니라 수정된 값을 대상 범위로 복사함을 나타냅니다.  `reverse` 알고리즘은 범위 내 요소의 순서를 반대로 바꾸며, `reverse_copy` 알고리즘은 또한 결과를 대상 범위로 복사합니다.  
  
 STL 알고리즘은 해당 목적 또는 요구 사항을 나타내는 그룹으로 분류되는 경우가 많습니다.  여기에는 요소 값을 변경하지 않는 비수정 알고리즘과 달리 요소 값을 변경하는 수정 알고리즘이 포함됩니다.  파생 알고리즘은 요소 값이 아닌 요소 순서를 변경합니다.  제거 알고리즘은 범위 또는 범위 복사본에서 요소를 제거할 수 있습니다.  알고리즘을 정렬하면 범위의 요소가 다양한 방법으로 정렬되며 정렬된 범위 알고리즘은 해당 요소가 특정 방식으로 정렬된 알고리즘에만 작동합니다.  
  
 숫자 처리를 위해 제공된 STL 숫자 알고리즘에는 고유 헤더 파일 [\<numeric\>](../standard-library/numeric.md)이 있으며, 함수 개체와 어댑터는 헤더 [\<functional\>](../standard-library/functional.md)에서 정의됩니다. 부울 값을 반환하는 함수 개체를 조건자라고 합니다.  기본 이진 조건자는 비교 `operator<`입니다.  일반적으로, 순서를 정하는 요소는 크기를 비교할 수 있어야 합니다. 즉, 제공된 어떤 두 요소에서 두 요소가 동일하거나\(어떤 것도 다른 것보다 작지 않음\) 하나가 다른 것보다 작음을 정할 수 있어야 합니다.  그러면 동일하지 않은 요소 사이에 순서가 지정됩니다.  
  
### 함수  
  
|||  
|-|-|  
|[adjacent\_find](../Topic/adjacent_find.md)|같지 않거나 지정한 조건을 충족하는 인접 요소 두 개를 검색합니다.|  
|[all\_of](../Topic/all_of.md)|지정한 범위에서 각 요소에 조건이 있을 경우 `true`를 반환합니다.|  
|[any\_of](../Topic/any_of.md)|요소의 지정된 범위에 조건이 한 번이라도 있을 경우 `true`를 반환합니다.|  
|[binary\_search](../Topic/binary_search.md)|정렬된 범위에 지정된 값과 같거나 이진 조건자가 지정한 의미에 따라 지정된 값과 같은 요소가 있는지 여부를 테스트합니다.|  
|[copy](../Topic/copy.md)|소스 범위의 요소를 대상 범위에 할당하여 요소의 소스 시퀀스 전체에서 반복하고 정방향으로 새 위치를 할당합니다.|  
|[copy\_backward](../Topic/copy_backward.md)|소스 범위의 요소를 대상 범위에 할당하여 요소의 소스 시퀀스 전체에서 반복하고 역방향으로 새 위치를 할당합니다.|  
|[copy\_if](../Topic/copy_if.md)|지정된 조건에 대해 `true`를 테스트하는 지정 범위의 모든 요소를 복사합니다.|  
|[copy\_n](../Topic/copy_n.md)|지정된 수의 요소를 복사합니다.|  
|[count](../Topic/count.md)|해당 값이 지정된 값과 일치하는 요소의 개수를 반환합니다.|  
|[count\_if](../Topic/count_if.md)|해당 값이 지정된 조건과 일치하는 요소의 개수를 반환합니다.|  
|[equal](../Topic/equal.md)|두 범위를 요소별로 비교하여 같음 여부 또는 이진 조건자가 지정한 의미의 동등성을 확인합니다.|  
|[equal\_range](../Topic/equal_range.md)|정렬된 범위에서 위치의 쌍을 찾습니다. 첫 번째는 지정된 요소의 위치보다 작거나 같으며 두 번째는 요소의 위치보다 큽니다. 여기서 시퀀스의 위치를 정하는 데 사용된 동등성 또는 순서 지정의 의미는 이진 조건자로 지정할 수 있습니다.|  
|[fill](../Topic/fill.md)|지정한 범위의 모든 요소에 동일한 새 값을 할당합니다.|  
|[fill\_n](../Topic/fill_n.md)|특정 요소로 시작하는 범위에서 지정된 개수의 요소에 새 값을 할당합니다.|  
|[find](../Topic/find%20\(STL\).md)|범위에서 지정된 값을 가진 요소가 첫 번째로 나타나는 위치를 찾습니다.|  
|[find\_end](../Topic/find_end.md)|범위에서 지정된 시퀀스와 동일하거나 이진 조건자가 지정한 의미와 동일한 마지막 하위 시퀀스를 찾습니다.|  
|[find\_first\_of](../Topic/find_first_of.md)|대상 범위 내에서 여러 값이 첫 번째로 나타나는 경우 또는 이진 조건자가 지정한 의미에서 지정된 요소 집합과 동일한 여러 요소가 첫 번째로 나타나는 경우를 검색합니다.|  
|[find\_if](../Topic/find_if.md)|범위에서 지정된 조건을 만족하는 요소가 첫 번째 나타나는 위치를 찾습니다.|  
|[find\_if\_not](../Topic/find_if_not.md)|표시된 범위에서 조건을 충족하지 않는 첫 번째 요소를 반환합니다.|  
|[for\_each](../Topic/for_each.md)|범위 내에서 정방향으로 각 요소에 지정된 함수 개체를 적용하고 함수 개체를 반환합니다.|  
|[generate](../Topic/generate.md)|범위에 있는 각 요소에 함수 개체에 의해 생성된 값을 할당합니다.|  
|[generate\_n](../Topic/generate_n.md)|함수 개체에 의해 생성된 값을 범위 내 지정된 수의 요소에 할당하고 마지막에 할당된 값 하나 다음의 위치로 반환합니다.|  
|[includes](../Topic/includes.md)|요소 간 순서 지정 또는 동등성 기준을 이진 조건자로 지정할 수 있을 경우 하나의 정렬된 범위가 두 번째 정렬된 범위에 포함된 모든 요소를 포함할 수 있는지 여부를 테스트합니다.|  
|[inplace\_merge](../Topic/inplace_merge.md)|두 연속 정렬 범위의 요소를 단일 정렬 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[is\_heap](../Topic/is_heap.md)|지정된 범위의 요소가 힙을 구성할 경우 `true`를 반환합니다.|  
|[is\_heap\_until](../Topic/is_heap_until.md)|지정된 범위가 마지막 요소까지 힙을 구성할 경우 `true`를 반환합니다.|  
|[is\_partitioned](../Topic/is_partitioned.md)|지정된 범위에서 조건에 대해 `true`를 테스트하는 모든 요소가 `false`를 테스트하는 요소 앞에 있을 경우 `true`를 반환합니다.|  
|[is\_permutation](../Topic/is_permutation.md)|지정된 범위의 요소가 올바른 순열을 만드는지 여부를 결정합니다.|  
|[is\_sorted](../Topic/is_sorted.md)|지정된 범위의 요소가 정렬된 순서로 되어 있을 경우 `true`를 반환합니다.|  
|[is\_sorted\_until](../Topic/is_sorted_until.md)|지정된 범위의 요소가 정렬된 순서로 되어 있을 경우 `true`를 반환합니다.|  
|[iter\_swap](../Topic/iter_swap.md)|지정된 반복기의 쌍이 참조하는 두 값을 교환합니다.|  
|[lexicographical\_compare](../Topic/lexicographical_compare.md)|두 시퀀스를 요소별로 비교하여 둘 중 작은 것을 결정합니다.|  
|[lower\_bound](../Topic/lower_bound.md)|정렬된 범위에서 지정된 값보다 크거나 같은 값을 갖는 첫 번째 요소의 위치를 찾습니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[make\_heap](../Topic/make_heap.md)|지정한 범위의 요소를 첫 번째 요소가 가장 큰 힙으로 변환합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[max](../Topic/max.md)|두 개체를 비교하고 둘 중 큰 개체를 반환합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[max\_element](../Topic/max_element.md)|지정된 범위에서 가장 큰 첫 번째 요소를 찾습니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[merge](../Topic/merge.md)|정렬된 두 소스 범위의 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[min](../Topic/min.md)|두 개체를 비교하고 둘 중 작은 개체를 반환합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[min\_element](../Topic/min_element.md)|지정된 범위에서 가장 작은 첫 번째 요소를 찾습니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[minmax](../Topic/minmax.md)|두 개의 입력된 매개 변수를 비교하여 작은 수와 큰 수의 순서로 구성된 한 쌍을 반환합니다.|  
|[minmax\_element](../Topic/minmax_element.md)|한 번의 호출로 [min\_element](../Topic/min_element.md) 및 [max\_element](../Topic/max_element.md)에서 수행하는 작업을 수행합니다.|  
|[mismatch](../Topic/mismatch.md)|두 범위를 요소별로 비교하여 같음 여부 또는 이진 조건자가 지정한 의미의 동등성을 확인하고 차이가 발생한 첫 번째 위치를 찾습니다.|  
|[이동](../Topic/%3Calg%3E%20move.md)|지정된 범위와 연결된 요소를 이동합니다.|  
|[move\_backward](../Topic/move_backward.md)|한 반복기의 요소를 다른 반복기로 이동합니다.  이동은 지정된 범위의 마지막 요소에서 시작하고 해당 범위의 첫 번째 요소에서 끝납니다.|  
|[next\_permutation](../Topic/next_permutation.md)|원래 순서 지정을 사전순에 따라 다음으로 큰 순열\(있는 경우\)로 대체할 수 있도록 범위의 요소 순서를 재정렬합니다. 여기서 다음의 의미는 이진 조건자로 지정할 수 있습니다.|  
|[none\_of](../Topic/none_of.md)|지정한 범위에서 요소 사이에 조건이 절대 없을 경우 `true`를 반환합니다.|  
|[nth\_element](../Topic/nth_element.md)|요소 범위를 분할하여 범위에서 시퀀스의 n번째 요소 앞의 모든 요소가 n번째 요소보다 작거나 같고 그 다음의 요소는 크거나 같도록 *n*번째 요소를 정확하게 찾습니다.|  
|[partial\_sort](../Topic/partial_sort.md)|범위에 있는 지정된 수의 더 작은 요소를 비내림차순 또는 이진 조건자로 지정한 정렬 기준에 따라 정렬합니다.|  
|[partial\_sort\_copy](../Topic/partial_sort_copy.md)|소스 범위의 요소를 대상 범위로 복사합니다. 여기서 소스 요소는 지정된 다른 이진 조건자보다 작거나 지정된 다른 이진 조건자로 정렬됩니다.|  
|[partition](../Topic/partition.md)|범위의 요소를 두 개의 연결되지 않은 집합으로 분류하고, 단항 조건자를 만족하는 요소는 만족하지 않는 요소보다 앞에 오도록 합니다.|  
|[partition\_copy](../Topic/partition_copy.md)|조건이 `true`인 요소를 한 대상으로 복사하고, 조건이 `false`인 요소를 다른 대상으로 복사합니다.  지정된 범위의 요소여야 합니다.|  
|[partition\_point](../Topic/partition_point.md)|지정된 범위에서 조건을 충족하지 않는 첫 번째 요소를 반환합니다.  조건을 충족하는 요소가 앞에, 그렇지 않는 요소는 뒤에 정렬됩니다.|  
|[pop\_heap](../Topic/pop_heap.md)|힙 맨 앞부터 범위의 끝에서 두 번째 위치 중에서 가장 큰 요소를 제거한 다음 나머지 요소로 새 힙을 구성합니다.|  
|[prev\_permutation](../Topic/prev_permutation.md)|원래 순서 지정을 사전순에 따라 다음으로 큰 순열\(있는 경우\)로 대체할 수 있도록 범위의 요소 순서를 재정렬합니다. 여기서 다음의 의미는 이진 조건자로 지정할 수 있습니다.|  
|[push\_heap](../Topic/push_heap.md)|범위의 마지막에 있는 요소를 범위의 이전 요소로 구성된 기존 힙에 추가합니다.|  
|[random\_shuffle](../Topic/random_shuffle.md)|범위의 *N*개 요소의 시퀀스를 무작위로 선택한 *N*\!  가능 배열 중 하나로 재정렬합니다.|  
|[remove](../Topic/remove.md)|나머지 요소의 순서에 영향을 미치거나 지정된 값이 없는 새 범위의 끝을 반환하지 않고 지정된 범위에서 지정된 값을 제거합니다.|  
|[remove\_copy](../Topic/remove_copy.md)|소스 범위의 요소를 대상 범위로 복사합니다. 단, 나머지 요소의 순서를 변경하거나 새 대상 범위의 끝을 반환하지 않고 지정된 값의 요소는 복사하지 않습니다.|  
|[remove\_copy\_if](../Topic/remove_copy_if.md)|소스 범위의 요소를 대상 범위로 복사합니다. 단, 나머지 요소의 순서를 변경하거나 새 대상 범위의 끝을 반환하지 않고 조건자를 만족하는 요소는 복사하지 않습니다.|  
|[remove\_if](../Topic/remove_if.md)|나머지 요소의 순서에 영향을 미치거나 지정된 값이 없는 새 범위의 끝을 반환하지 않고 지정된 범위에서 조건자를 만족하는 요소를 제거합니다.|  
|[replace](../Topic/replace.md)|범위의 각 요소를 검사하고 요소가 지정된 값과 일치하면 대체합니다.|  
|[replace\_copy](../Topic/replace_copy.md)|소스 범위의 각 요소를 검사하고 요소가 지정된 값과 일치하면 대체하는 동시에 결과를 새 대상 범위로 복사합니다.|  
|[replace\_copy\_if](../Topic/replace_copy_if.md)|소스 범위의 각 요소를 검사하고 요소가 지정된 조건자를 충족하면 대체하는 동시에 결과를 새 대상 범위로 복사합니다.|  
|[replace\_if](../Topic/replace_if.md)|범위의 각 요소를 검사하고 요소가 지정된 조건자를 충족하면 대체합니다.|  
|[reverse](../Topic/reverse.md)|범위 내에서 요소의 순서를 반대로 바꿉니다.|  
|[reverse\_copy](../Topic/reverse_copy.md)|소스 범위 내의 요소의 순서를 바꾸는 동시에 요소를 대상 범위로 복사합니다.|  
|[rotate](../Topic/rotate.md)|인접한 두 범위에 있는 요소를 교환합니다.|  
|[rotate\_copy](../Topic/rotate_copy.md)|소스 범위 내의 인접한 두 범위의 요소를 교환하고 결과를 대상 범위로 복사합니다.|  
|[search](../Topic/search.md)|대상 범위 내에서 시퀀스의 요소가 지정된 요소 시퀀스와 동일하거나 이진 조건자가 지정한 의미에 따라 지정된 시퀀스의 요소와 동일한 첫 번째 시퀀스를 검색합니다.|  
|[search\_n](../Topic/search_n.md)|범위에서 특정 값의 요소가 지정된 수만큼 있거나 이진 조건자가 지정한 해당 값과 관련이 있는 첫 번째 하위 시퀀스를 검색합니다.|  
|[set\_difference](../Topic/set_difference.md)|한 정렬된 소스 범위에 속하지만 두 번째 정렬된 소스 범위에 속하지 않는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[set\_intersection](../Topic/set_intersection.md)|정렬된 두 소스 범위에 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[set\_symmetric\_difference](../Topic/set_symmetric_difference.md)|정렬된 두 소스 범위 중 하나에만 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[set\_union](../Topic/set_union.md)|정렬된 두 소스 범위 중 하나 이상에 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
|[sort](../Topic/sort.md)|지정된 범위에 있는 요소를 비내림차순 또는 이진 조건자로 지정한 정렬 기준에 따라 정렬합니다.|  
|[shuffle](../Topic/std::shuffle.md)|난수 생성기를 사용하여 지정된 범위 내 요소의 순서를 섞습니다\(다시 정렬\).|  
|[sort\_heap](../Topic/sort_heap.md)|힙을 정렬된 범위로 변환합니다.|  
|[stable\_partition](../Topic/stable_partition.md)|범위의 요소를 두 개의 연결되지 않은 집합으로 분류하고, 단항 조건자를 만족하는 요소는 만족하지 않는 요소보다 앞에 오도록 하여 동등한 요소의 상대적 관계를 유지합니다.|  
|[stable\_sort](../Topic/stable_sort.md)|지정된 범위에 있는 요소를 비내림차순 또는 이진 조건자로 지정한 정렬 기준에 따라 정렬하고 동등한 요소의 상대적 관계를 유지합니다.|  
|[스왑](../Topic/swap.md)|두 가지 형식의 개체 사이에서 요소 값을 교환하여 첫 번째 개체의 내용을 두 번째 개체에 할당하고 두 번째 개체의 내용을 첫 번째 개체에 할당합니다.|  
|[swap\_ranges](../Topic/swap_ranges.md)|한 범위의 요소를 크기가 동일한 다른 범위의 요소로 교환합니다.|  
|[변환\(Transform\)](../Topic/transform.md)|두 소스 범위에서 요소 쌍에 또는 소스 범위에 있는 각 요소에 지정된 함수 개체를 적용하고 대상 범위에 함수 개체의 반환 값을 복사합니다.|  
|[unique](../Topic/unique%20\(%3Calgorithm%3E\).md)|지정된 범위에서 서로 인접한 중복 요소를 제거합니다.|  
|[unique\_copy](../Topic/unique_copy.md)|서로 인접한 중복 요소를 제외하고 소스 범위의 요소를 대상 범위로 복사합니다.|  
|[upper\_bound](../Topic/upper_bound.md)|지정된 값보다 큰 값을 갖는 정렬된 범위에 있는 첫 번째 요소의 위치를 찾습니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)