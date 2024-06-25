<script lang="ts">
	import {
		List,
		Card,
		Header,
		Footer,
		Content,
		Section,
		ListItem,
		CardTitle,
		CardDescription,
	} from '$lib/components/ui';
</script>

<title>Algorithms</title>
<Header align="center">Algorithms</Header>
<Content>
	<Section title="Sorting Algorithms">
		<Card>
			<CardTitle>Selection Sort</CardTitle>
			<CardDescription
				>Selection sort is a simple and efficient sorting algorithm that works by repeatedly
				selecting the smallest (or largest) element from the unsorted portion of the list and moving
				it to the sorted portion of the list.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Bubble Sort</CardTitle>
			<CardDescription>
				In Bubble Sort algorithm, traverse from left and compare adjacent elements and the higher
				one is placed at right side. In this way, the largest element is moved to the rightmost end
				at first. This process is then continued to find the second largest and place it and so on
				until the data is sorted.
			</CardDescription>
			<List name="Pros">
				<ListItem>
					<b>Simplicity</b>: It's incredibly easy to understand and implement, making it a great
					introduction to sorting algorithms.
				</ListItem>
				<ListItem>
					<b>Memory Efficiency</b>: Bubble Sort is an in-place algorithm, meaning it sorts the data
					within the existing list without requiring additional memory for temporary storage.
				</ListItem>
				<ListItem>
					<b>Nearly Sorted Data</b>: If the data is already partially sorted, Bubble Sort can be
					surprisingly efficient as it only needs a few passes to complete the sorting
				</ListItem>
			</List>
			<List name="Cons">
				<ListItem>
					<b>Inefficiency</b>: For large datasets, Bubble Sort becomes very slow. Its time
					complexity is O(n^2), meaning the sorting time increases dramatically with the number of
					elements. This is because it makes numerous comparisons and swaps even when the data is
					mostly sorted.
				</ListItem>
				<ListItem>
					<b>Unnecessary Swaps</b>: Bubble Sort might perform many unnecessary comparisons and
					swaps, especially on nearly sorted data.
				</ListItem>
			</List>
		</Card>
		<Card>
			<CardTitle>Merge Sort</CardTitle>
			<CardDescription>
				Merge Sort tackles a messy list like a master organizer. It divides the list in half
				repeatedly until it reaches single elements (already sorted sub-lists). Then, it cleverly
				merges these sorted sub-lists back together, comparing elements from each half and placing
				the smaller one into the final sorted list. This <b>"divide-and-conquer"</b> strategy makes Merge
				Sort a fast and efficient way to sort information, working like a pro at shuffling smaller sorted
				chunks into a single, perfectly organized list.
			</CardDescription>
		</Card>
	</Section>
	<Section title="Searching Algorithms">
		<Card>
			<CardTitle>Selection Sort</CardTitle>
			<CardDescription
				>Selection sort is a simple and efficient sorting algorithm that works by repeatedly
				selecting the smallest (or largest) element from the unsorted portion of the list and moving
				it to the sorted portion of the list.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Bubble Sort</CardTitle>
			<CardDescription>
				In Bubble Sort algorithm, traverse from left and compare adjacent elements and the higher
				one is placed at right side. In this way, the largest element is moved to the rightmost end
				at first. This process is then continued to find the second largest and place it and so on
				until the data is sorted.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Merge Sort</CardTitle>
			<CardDescription>
				Merge Sort tackles a messy list like a master organizer. It divides the list in half
				repeatedly until it reaches single elements (already sorted sub-lists). Then, it cleverly
				merges these sorted sub-lists back together, comparing elements from each half and placing
				the smaller one into the final sorted list. This 'divide-and-conquer' strategy makes Merge
				Sort a fast and efficient way to sort information, working like a pro at shuffling smaller
				sorted chunks into a single, perfectly organized list.
			</CardDescription>
		</Card>
	</Section>
</Content>
<Footer align="center">© 2024 Pathum Senanayake</Footer>
