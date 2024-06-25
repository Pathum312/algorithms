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
			<CardDescription>
				Selection Sort acts like a teacher organizing students for a photo. It starts by assuming
				the first student is the <b>"shortest"</b> (or depending on your sorting need,
				<b>"tallest"</b>). Then, it scans the entire class to find the actual shortest student. The
				teacher (the algorithm) then swaps the places of these two students, putting the shortest
				one at the front of the line (like the beginning of the list). This process repeats, each
				time finding the remaining shortest student from the unsorted part of the line and swapping
				them into their correct position. By the end, just like a perfectly organized photo, the
				list is sorted.
			</CardDescription>
			<List name="Pros">
				<ListItem>
					<b>Simple and Easy to Understand</b>: Like Bubble Sort, Selection Sort is straightforward
					to grasp and implement, making it a good introduction to sorting algorithms.
				</ListItem>
				<ListItem>
					<b>In-place Sorting</b>: It sorts the data within the existing list, requiring no
					additional memory for temporary storage.
				</ListItem>
				<ListItem>
					<b>Nearly Sorted Data</b>: Similar to Bubble Sort, Selection Sort can be efficient for
					partially sorted data as it only needs to find the remaining minimum/maximum elements.
				</ListItem>
			</List>
			<List name="Cons">
				<ListItem>
					<b>Inefficient for Large Datasets</b>: Just like Bubble Sort, Selection Sort suffers from
					a time complexity of O(n^2). This means sorting time increases significantly with the
					number of elements due to numerous comparisons needed throughout the process.
				</ListItem>
				<ListItem>
					<b>Unnecessary Swaps</b>: Selection Sort might perform unnecessary comparisons and swaps,
					especially on nearly sorted data.
				</ListItem>
			</List>
		</Card>
		<Card>
			<CardTitle>Bubble Sort</CardTitle>
			<CardDescription>
				Bubble Sort works like a patient lifeguard checking swimmers on a beach. It starts at one
				end of the list and compares neighboring elements. If they're out of order (taller swimmer
				behind a shorter one), it swaps them. This <b>"bubbling"</b> action pushes the larger element
				one position further back like the lifeguard gently nudging a swimmer back. The process repeats
				for the entire list, with each pass guaranteeing the largest element seen so far is now at the
				end. This continues until no swaps are needed, signifying a perfectly sorted list, just like
				a calm beach with swimmers in the right order.
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
			<List name="Pros">
				<ListItem>
					<b>Efficiency</b>: Merge sort boasts a time complexity of O(n log n) in all cases (best,
					average, and worst). This means it scales well for large datasets, making it a great
					choice for sorting big collections of data.
				</ListItem>
				<ListItem>
					<b>Stability</b>: Merge sort is a stable sorting algorithm. This means that if you have
					duplicate elements in your list, their original order is preserved after sorting.
				</ListItem>
				<ListItem>
					<b>Simplicity</b>: The core concept of merge sort (divide, conquer, and merge) is
					relatively easy to understand, making it a good choice for beginners to learn about
					sorting algorithms.
				</ListItem>
			</List>
			<List name="Cons">
				<ListItem>
					<b>Space complexity</b>: Unlike some in-place sorting algorithms (which modify the
					original data), merge sort requires additional memory to store sublists during the merge
					process. This can be a drawback for situations with limited memory availability.
				</ListItem>
				<ListItem>
					<b>Overhead for small lists</b>: For very small lists, the overhead of dividing the list
					and merging sublists can outweigh the benefits of merge sort. In these cases, simpler
					algorithms like insertion sort might be more efficient.
				</ListItem>
			</List>
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
