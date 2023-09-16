import re
from collections import defaultdict
import matplotlib.pyplot as plt

# Define a pattern to extract author names and messages
pattern = r'\[.*?\] ([^:]+): (.+)'

# Initialize a dictionary to count messages per author
message_counts = defaultdict(int)

# Read the text from the file
with open("C:/Users/sedat/Downloads/chat.txt", "r", encoding="utf-8") as file:
    for line in file:
        match = re.match(pattern, line)
        if match:
            author, message = match.groups()
            message_counts[author] += 1

# Sort the message counts from highest to lowest
sorted_message_counts = sorted(message_counts.items(), key=lambda x: x[1], reverse=True)

# Extract authors and message counts for plotting
authors, counts = zip(*sorted_message_counts)

# Create a bar chart
plt.figure(figsize=(10, 6))
plt.bar(authors, counts)
plt.xlabel("Authors")
plt.ylabel("Number of Messages")
plt.title("Number of Messages Sent by Each Author (Highest to Lowest)")
plt.xticks(rotation=90)
plt.tight_layout()

# Display the chart
plt.show()
