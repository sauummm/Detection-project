import cv2
import os
from ultralytics import YOLO  # Ensure you have installed `ultralytics`

# Path to the input image
image_path = '2h&0.jpeg'  # Replace with your actual image file

if os.path.exists(image_path):
    image = cv2.imread(image_path)
    
    if image is not None:  
        # Initialize the YOLO model
        model = YOLO('yolov8n.pt')  # Use quotes around the file name
        
        # Run the model on the input image
        results = model(image, conf=0.5)  # Confidence threshold of 50%
        
        # Loop through the detection results
        for result in results:
            boxes = result.boxes.xyxy  # Get bounding box coordinates
            scores = result.boxes.conf  # Confidence scores
            class_ids = result.boxes.cls  # Class IDs

            for box, score, class_id in zip(boxes, scores, class_ids):
                x1, y1, x2, y2 = map(int, box)  # Convert box to integers
                label = f"{model.names[int(class_id)]}: {score:.2f}"

                # Draw the bounding box and label on the image
                cv2.rectangle(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
                cv2.putText(image, label, (x1, y1 - 10), cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 255, 0), 2)

        # Display the output image
        cv2.imshow("Input Image", image)
        cv2.waitKey(0)
        cv2.destroyAllWindows()

    else:
        print(f"Error: Could not read image at {image_path}. Check if the file is a valid image format.")
else:
    print(f"Error: Image file not found at {image_path}")
