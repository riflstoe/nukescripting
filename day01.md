node selection

1. nuke.selectedNode()
    - 선택된 노드
2. nuke.selectedNodes()
    - 선택된 노드들
    - lists = nuke.selectedNodes()
    - 마지막에 선택된 노드가 0이다. 드래그해서 선택해도 선택된 역순으로 번호가 지정됨
3. the_node = nuke.toNode(’grade1’)
    - nuke.toNode() 는 특정 노드를 찾아 그 노드를 선택해준다
4. the_node.input(0).knob(’postage_stamp’).setValue(False)
    - input(n) 은 특정 노드에 연결된 노드를 선택해준다
    - 순서대로 0부터 시작한다. Merge의 경우 B→A→Roto→A2→… 순서다.

property change

1. the_node.knob(’postage_stamp’).setValue(False)
    
    the_node.knob(’black’).setValue(20)
    
    - knob().setvalue() 는 노드 안의 property 값을 바꿔준다.
    - 입력 형식이 맞아야 한다. 상수 정수 스트링 등
2. for the_node in nuke.selectedNodes():
    
    the_node.knob(’disable’).setValue(False)
    
    - for문을 사용해 선택된 노드들의 모든 property를 바꿀 수 있다
    - dot, sticky note, noop 등은 property가 매우 적은 노드들을 같이 선택시 작동하지 않는다
        - 선택을 걸러내야 한다

indexing

1. [start:stop:step]
2. “penguin.dance.####.exr”.split(’.’)[-2]
    
    “gentoo.penguin.dance.####.exr”.split(’.’)[-2]
    
    - 전부 ####를 가져온다
