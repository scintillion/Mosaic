<script lang="ts">
	import { onMount } from 'svelte';
	import { LOLEditor } from '$lib/ConstListEditor';
	import { RSLst } from '../../lib/ConstList';

	onMount(() => {
		const container: HTMLDivElement = document.getElementById(
			'ListOfListsContainer'
		) as HTMLDivElement;
		const list1: RSLst.constList = new RSLst.constList(
			'Test1|Name:[%=Jane]Your Name|XY:[#=1]A Number Value|'
		);
		const list2: RSLst.constList = new RSLst.constList(
			'Test2|Name:[%=John]Your Name|XY:[#=2]A Number Value|'
		);
		const list3: RSLst.constList = new RSLst.constList(
			'Test3|Name:[%=Jacob]Your Name|XY:[#=3]A Number Value|'
		);
		const LoL: RSLst.ListOfLists = new RSLst.ListOfLists();
		LoL.Add(list1.Str);
		LoL.Add(list2.Str);
		LoL.Add(list3.Str);

		const LoLEditor: LOLEditor = new LOLEditor(LoL, container);
		LoLEditor.Populate();
	});
</script>

<div id="ListOfListsContainer" />

<style lang="scss">
	#ListOfListsContainer {
		width: 100vw;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		gap: 25px;
	}
</style>
