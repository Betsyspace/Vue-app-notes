# Vue-app-notes
��������ô��Ŀ���ܽ�

####1����ֱ���в���
```
<li>
   <span>
     ���˾����ײ�
   </span>
</li>
- �������span��Ԫ����liԪ���д�ֱ����
- ��ʽ���ã�
li{ display:table; }
span{ display:table-cell;vertical-align:middle; }
```
####2��flex����
```
<div class="wrapper">
	<div class="icon"></div>
	<div class="text"></div>
</div>
-������̶����,�ұ�����Ӧ
-��ʽ����
.wrapper{ display:flex; }
.icon{ flex: 0 0 80px; width:80px; }
.text{ flex: 1 }
```

####3���ƶ���1px���ر߿�
```
-scssд��
��һ����
@mixin border1px($color){
  position: relative;
  &:after{
    display: block;
    position: absolute;
    left: 0;
    bottom: 0;
    width:100%;
    border-top: 1px solid $color;
    content:' ';
  }
}
�ڶ�����ý���ѯ����border-1px��ʽ
@media (-webkit-device-pixel-ratio: 1.5),(min-device-aspect-ratio: 3/2){
  .border-1px{
    &::after{
      -webkit-transform: scaleY(0.7);
      transform: scaleY(0.7);
    }
  }
}

@media (-webkit-device-pixel-ratio: 2),(min-device-aspect-ratio: 4/2){
  .border-1px{
    &::after{
      -webkit-transform: scaleY(0.5);
      transform: scaleY(0.5);
    }
  }
}

-���� ����Ҫ�ӱ߿��Ԫ�ص���mixin��ͬʱ����border-1px��class
@include border1px(rgb(0,0,0));
```

####4����ĳ����������ĳ����ʽhighlight
```
<div :class="{ 'highlight':totalCount>0 }"></div>
- д��
- :class = "{ '��ʽ' : ���� }"
```

####5��������Ҫ��ʱ�ı�����ݶ���д��computed�������Ե���

####6������DOMԪ����v-el��ͨ��this.$els����

####7�������������v-ref��ͨ��this.$refs����

####8������¼���ֹ�¼�ð��д����@click.stop.prevent="xxx"

####9��ͼƬ�����ֶ��뷽ʽ �ֱ�����display:inline-block;vertical-align:top;